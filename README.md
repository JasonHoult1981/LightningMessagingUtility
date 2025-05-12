

Lightning Messaging Utility

Lightning Messaging Utility is a Salesforce Labs component designed to make it easier for Admins and Developers to display contextual, reusable, and configurable toast messages across Lightning Experience and Lightning Web Components (LWC).

This lightweight utility helps you guide users through key interactions by providing real-time feedback, error alerts, success confirmations, and informative messages in a declarative or programmatic way.

⸻

Features
	•	Display toast messages from Flows or Apex
	•	Configurable toast type: Success, Error, Info, Warning
	•	Works seamlessly in Lightning Experience and LWC
	•	Simple installation and setup
	•	Supports reusable message templates
	•	Fully open source and customizable

⸻

Use Cases
	•	Notify users after Flow actions complete
	•	Display confirmation or validation messages from custom Apex
	•	Provide inline feedback during guided processes
	•	Alert users to important changes or system updates

⸻

Installation
	1.	Clone this repository:

git clone https://github.com/SalesforceLabs/LightningMessagingUtility.git


	2.	Deploy to your org using Salesforce CLI:

sfdx force:source:deploy -p force-app


	3.	Assign permissions if required via permission set included in the package.

⸻

Usage

From Flow

Use the Show Toast Message invocable Apex action. Provide the following inputs:
	•	Title – The title of your message
	•	Message – The body of the toast
	•	Type – Success, Error, Info, or Warning

From Apex

LightningToast.show('Success!', 'Record updated successfully.', 'success');

From LWC

You can import and dispatch a standard toast event:

import { ShowToastEvent } from 'lightning/platformShowToastEvent';

this.dispatchEvent(
  new ShowToastEvent({
    title: 'Success',
    message: 'Your record was saved.',
    variant: 'success'
  })
);


⸻

Contributing

We welcome pull requests and suggestions! This is a Salesforce Labs community-supported project. Feel free to fork, modify, and share your improvements.

⸻

License

BSD 3-Clause License

⸻

Would you like me to generate a sample Flow using the component or a video walkthrough script to accompany this README?

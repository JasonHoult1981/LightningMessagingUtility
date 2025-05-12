
# Lightning Messaging Utility

**Lightning Messaging Utility** is a Salesforce Labs component designed to help Admins and Developers display contextual, reusable, and configurable toast messages across Lightning Experience and Lightning Web Components (LWC).

This lightweight utility provides real-time user feedback through success messages, error alerts, warnings, and informational messages—ideal for enhancing user experience during Flows or custom development.

---

## Features

- Display toast messages from Flows or Apex
- Configurable toast type: `Success`, `Error`, `Info`, or `Warning`
- Works seamlessly in Lightning Experience and LWC
- Simple installation and setup
- Supports reusable message templates
- Fully open source and customizable

---

## Use Cases

- Notify users after Flow actions complete
- Display validation results or process outcomes
- Provide inline messaging during guided experiences
- Alert users to important business logic exceptions

---

## Installation

1. **Clone this repository**  
   ```bash
   git clone https://github.com/SalesforceLabs/LightningMessagingUtility.git
   ```

2. **Deploy to your org** using Salesforce CLI  
   ```bash
   sfdx force:source:deploy -p force-app
   ```

3. **Assign permissions**  
   If a permission set is included, assign it to users who will invoke messaging features.

---

## Usage

### From Flow

Use the **Show Toast Message** invocable Apex action in Flow Builder.

**Inputs:**
- `Title`: Text displayed in bold at the top of the message
- `Message`: Main body text of the toast
- `Type`: One of `success`, `error`, `info`, or `warning`

### From Apex

```apex
LightningToast.show('Success!', 'Record updated successfully.', 'success');
```

### From LWC

Use the standard `ShowToastEvent`:

```js
import { ShowToastEvent } from 'lightning/platformShowToastEvent';

this.dispatchEvent(
  new ShowToastEvent({
    title: 'Success',
    message: 'Your record was saved.',
    variant: 'success'
  })
);
```

---

## Contributing

We welcome pull requests and community contributions! Fork the repo, make your updates, and submit a PR. For significant changes, please open an issue first to discuss your proposed changes.

---

## License

This project is licensed under the [BSD 3-Clause License](LICENSE).

---

## Maintainers

This component is maintained by Salesforce Labs. Community support is provided on a best-effort basis.

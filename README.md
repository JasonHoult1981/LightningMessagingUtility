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

---

## Demo Org Setup Instructions

To quickly test and explore the Lightning Messaging Utility, follow these steps to set it up in a Salesforce Developer or Sandbox org:

### 1. **Sign Up or Log In to a Salesforce Org**
- Sign up for a free Developer Edition org at [developer.salesforce.com/signup](https://developer.salesforce.com/signup), or
- Use an existing Sandbox org.

### 2. **Install the Component**
You can install the component using Salesforce CLI or deploy metadata directly.

**Option A: Salesforce CLI**
```bash
git clone https://github.com/SalesforceLabs/LightningMessagingUtility.git
cd LightningMessagingUtility
sfdx force:source:deploy -p force-app
```

**Option B: Use Workbench**
1. Zip the `force-app/main/default` directory contents.
2. Go to [workbench.developerforce.com](https://workbench.developerforce.com).
3. Login and navigate to:
   `Migration > Deploy`
4. Upload the ZIP file and deploy.

### 3. **Assign Permission Set (If Provided)**
If the repository includes a permission set (e.g., `LightningMessagingUtilityUser`), assign it to your user:
```bash
sfdx force:user:permset:assign -n LightningMessagingUtilityUser
```

### 4. **Test the Component in Flow Builder**
1. Go to **Setup > Flows**.
2. Create a new **Screen Flow**.
3. Add the **"Show Toast Message"** Apex action.
4. Configure:
   - `Title`: e.g., `Welcome`
   - `Message`: e.g., `You’ve launched this demo successfully!`
   - `Type`: `success`
5. Save & Activate the Flow.
6. Run the Flow in the Flow Debugger or embed in a Lightning page to see the message in action.

### 5. **Use in LWC or Apex (Optional)**
Refer to the **Usage** section of this README for examples on calling the utility from LWC or Apex code.

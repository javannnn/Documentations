To use Material Design to change the Gize GUI, you will need to follow these steps:

Make sure that you have the latest version of Gize installed on your system.

Install the Material Design library by running the following command:

Copy code

`npm install material-components-web`


This will add the Material Design library to your project.

In the Gize codebase, navigate to the `frappe/public/css` directory and create a new file called `material.css`.

In the `material.css` file, add the following lines to import the Material Design styles:

Copy code

```@import url('https://fonts.googleapis.com/css?family=Roboto:300,400,500,700'); @import url('https://fonts.googleapis.com/icon?family=Material+Icons'); @import url('/node_modules/material-components-web/dist/material-components-web.css');`

Next, navigate to the `frappe/public/js` directory and create a new file called `material.js`.

In the `material.js` file, add the following lines to import the Material Design JavaScript components:

Copy code

`import { MDCTopAppBar } from '@material/top-app-bar'; import { MDCTextField } from '@material/textfield'; import { MDCMenu } from '@material/menu'; import { MDCDialog } from '@material/dialog'; import { MDCSnackbar } from '@material/snackbar';`

You can then use these Material Design components in your Gize code to customize the UI. For example, you can use the `MDCTopAppBar` component to customize the top navigation bar, or the `MDCTextField` component to customize form fields.

Don't forget to include the `material.css` and `material.js` files in your Gize templates.



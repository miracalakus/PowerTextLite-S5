## I regret to inform you that I am unable to share the development code, as my internship company does not permit its publication. However, I would be more than happy to discuss and explain my work in detail during an interview.
# PowerText Lite Frontend

PowerText Lite is a powerful tool designed to transform product data into compelling product descriptions. Leveraging the capabilities of OpenAI, this tool simplifies and enhances the process of creating engaging content.

## Introduction

To begin, users are required to upload a .xlsx file based on the provided template. Subsequently, users must configure settings by specifying the product category, selecting the output-language, determining the tone of voice, setting a maximum word limit, and finally, filtering the desired features.

## Features

![](ReadmeFiles/Screen%20Recording%202024-01-11%20at%2012.03.26.mov)

PowerText Lite is exclusively designed for effortlessly crafting product descriptions. The user begins by uploading a .xlsx file based on the provided template. After the upload, the user configures several settings for the product description.

As a first step, the user fills in the product category, corresponding to the category of the products in the uploaded file. Next, the user selects the desired output language. Here, the user can also opt for multiple languages simultaneously, with each language presented in a separate paragraph. The tool then allows the user to choose the tone of voice, enabling a more targeted product description for the intended target-audience.

Following that, the user needs to filter the desired features. The available features are derived from the first row of the uploaded .xlsx file, where the titles of the features are displayed. From this, the tool extracts the features, and the user can choose those desired for the product description.

Subsequently, the user selects the maximum number of words for the generated product description. This determines the length of the text to be generated. After configuring these settings, the user can preview and proceed to generate the product description. The result can be downloaded, and if no longer needed, the generated file can be deleted.

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```
```sh
npm install
```

## Technologies Used

- Vue 3 version 3.2.47
- Vuetify version 3.4.8
- ImportJS
- Tawk.to integration

## Styling

In the development of PowerText Lite, Vuetify components have been utilized. In subsequent stages of development, it is imperative to maintain consistent styling for buttons and colors to ensure a cohesive design.

The frontend of PowerText Lite is based on the Figma prototype that was made and tested before development.
- The link to this file: `https://www.figma.com/file/GVo7nO9xIH1KIM4mgYrfn7/High-fidelity-prototype-versie-3?type=design&node-id=0%3A1&mode=design&t=7GVavf2CllOP83fV-1`
- Link to the prototype:`https://www.figma.com/proto/GVo7nO9xIH1KIM4mgYrfn7/High-fidelity-prototype-versie-3?page-id=0%3A1&type=design&node-id=1-1208&viewport=777%2C458%2C0.05&t=AkvBvEl8Bh7fN45d-1&scaling=min-zoom&mode=design`

### Most common components

- `<V-card>:` This component often adopts the color `#206A8E`. It is used as a background for sections where the majority of interactions occur.
- `<v-text-field>:` These are text fields where users can input desired data.
- `<v-card-title>, <v-card-subtitle>, <v-card-text>:` These represent the titles, subtitles, and text. The colors of these components are either `#ffffff` or `#000`, depending on the background colors.

- `V-btn:` This is the component for the buttons. Colors may vary based on their respective functions. 
  - `Start:` `#D57F2E`
  - `Delete` `rgb(255,0,0)`
  - `Progress` `#D57F2E`
  - `Download` `#34A853`

All the other buttons must be `#D57F2E`

To maintain a consistent design, refer to the `base.css` file. It contains additional choices regarding the size and positioning of components. In the event of deviations from design choices, please discuss this first with the marketing team within Squadra MLC. For an overview of all the design guidelines, refer to the [brand guidelines](src/docs/PT-Lite-Brand-Guideline.png). 

## Status

The foundation for PowerText Lite has been established, but certain components require adjustments or enhancements before the complete tool can be offered to clients.

### Navigation Bar

Currently, only one out of four buttons in the navigation bar is functional. It is recommended to reconsider the navigation bar's capabilities or potentially remove it.

### Registration

The registration page and its associated UI are ready and linked to the backend. However, there is a limit to the number of "keys" in the backend, while users can currently input unlimited characters, which is unintended. It is advised to review error handling and make necessary adjustments.

Another issue is that users do not receive emails upon creating an account. Currently, a link is sent in Docker for email confirmation. Clicking this link leads to a blank page due to incomplete Stripe integration. Manual steps, such as assigning a subscriber ID and setting a subscription end date in TablePlus, are required.

### Forgot Password

The UI is ready and linked to the backend, but users do not receive emails to set a new password. Error handling and necessary adjustments need to be implemented. Currently, users do not automatically return to the login page after changing the password, impacting user experience.

### Account Managment

There is currently no page for users to view and manage their account details, and no wireframes have been created. It is recommended to follow the UI of other pages for a consistent design. According to PowerText Lite requirements, the page should include:

- Overview of account details
- Ability to modify data
- Overview of linked credit card details (potentially with a link to Stripe)
- Ability to remove/modify credit card details
- Ability to delete the account
- Error handling for updating account details

### Stripe Integration

Stripe is the only integrated payment method, but integration is incomplete. Customers without a subscription are directed to the Stripe website to log in or create an account and link a credit card. It is advised to test and make the integration fully operational. Consultation with the product owner regarding desired subscriptions is recommended.

### Google Sign-In-API

There is no integration with the Google Sign-In API.

### Invoices

Customers should receive invoices in their mailbox, but this is not happening. It is crucial to ensure that invoices are generated and sent to customers.

### Files Overwiew

The foundation for the UI of this page is laid out, but the table overview should be made clearer with column names and better-aligned elements. Sorting and/or filtering functions can be added. The "start generating" button needs a more prominent placement.

### Configure/Upload file Dialog

The foundation is present, but error handling needs improvement. Verification of the correct file format (.xlsx) is currently lacking. Error handling for filled values to prevent endless input is necessary. Clear explanations, especially when choosing/filling data, are crucial. This could be made in the form of "tooltips". Formatting on the review page can be enhanced. The dialog should refresh automatically after generating.

### Output File

The current output file does not meet requirements. It should have three columns: an ID per product for distinction, a column with plain text product descriptions, and an ID with the same product description in HTML format. Users should also have the ability to download the output file in CSV format, which is currently not possible.

### Generation

The generation process appears to take too long. Thorough research and improvements are needed. The prompt also does not work optimally; it is advised to pass only the selected features instead of all features from the file. Ensure the provided template file is correct.

# Advanced Customization

This guide is designed for users who want to go beyond basic theme customization and delve into more advanced modifications. Whether you're adding custom CSS, integrating custom JavaScript, or tweaking Liquid templates, this guide will provide you with the knowledge and best practices to safely and effectively customize your Shopify theme.

## Custom CSS

Customizing your theme’s appearance with CSS allows you to tailor the design to your specific needs, providing a unique look and feel that aligns with your brand. By adding custom CSS, you can make detailed adjustments that aren't always available through the default theme settings, giving you greater control over the visual aspects of your online store.

### Adding Custom Styles

There are a couple of ways you can add custom CSS to your Shopify theme. You can either use the theme editor or directly edit the theme files through the code editor. Both methods allow you to enhance your store's appearance with custom styles.

#### Theme Editor

To access and edit custom CSS via the theme editor in your Shopify admin, follow these steps:

1. **Log in to Shopify Admin:**

   - Visit [shopify.com](https://www.shopify.com) and log in using your store's credentials.

2. **Navigate to Online Store:**

   - From the Shopify Admin dashboard, click on **"Online Store"** in the left-hand menu. This will expand a sub-menu.

3. **Select Themes:**

   - Under **"Online Store"**, click on **"Themes"**. You'll be taken to a page that displays your current theme as well as any other themes you have installed.

4. **Customize the Theme:**

   - On the Themes page, locate your active theme (marked as "Current Theme") and click the **"Customize"** button next to it. This will open the theme editor, where you can modify your theme’s styles and settings.

5. **Navigate to the Custom CSS:**

   - In the theme editor, locate the left-hand sidebar and scroll down to **"Custom CSS"** at the bottom. Click on it to expand the settings.

6. **Add Custom CSS Styles:**

   - Enter your custom CSS styles into the provided field.

7. **Save Your Changes:**

   - After making adjustments, click **"Save"** to apply the new styles to your theme.

#### Code Editor

To add custom CSS by creating a custom CSS file in the theme code editor, follow these steps:

1. **Log in to Shopify Admin:**

   - Visit [shopify.com](https://www.shopify.com) and log in using your store's credentials.

2. **Navigate to the Code Editor:**

   - From the Shopify Admin dashboard, click on **"Online Store"** in the left-hand menu.
   - Under **"Themes"**, find your active theme (marked as "Current Theme") and click on the **"Actions"** dropdown.
   - Select **"Edit code"** from the dropdown menu. This will open the theme code editor, where you can modify the underlying files of your theme.

3. **Add a Custom CSS File:**

   - In the code editor, locate the **"Assets"** folder in the left-hand sidebar.
   - Click on the **"Add a new asset"** button at the top of the Assets section.
   - In the pop-up window, select **"Create a blank file"** and name it something like `custom.css`. Ensure the file extension is `.css`.
   - Click **"Add asset"** to create the new file. This file will now appear in the Assets folder.

4. **Reference the CSS File in Your Theme:**

   - Still in the theme code editor, navigate to the **"Layout"** folder and select the `theme.liquid` file.
   - In the `theme.liquid` file, locate the closing `</head>` tag, which is typically near the top of the file.
   - Just before the `</head>` tag, add the following line of code to include your custom CSS file:
     ```liquid
     <link href="{{ 'custom.css' | asset_url }}" rel="stylesheet">
     ```

5. **Save Your Changes:**

   - After adding your custom CSS file and referencing it in the `theme.liquid` file, click **"Save"** in the top right corner of the code editor to apply your changes.

### Best Practices

When adding custom CSS to your Shopify theme, following best practices ensures that your styles are effective, maintainable, and won't cause unexpected issues down the line.

- **Avoid Overwriting Core Files:** To protect your theme from accidental overwrites during updates, avoid editing core theme files directly. Instead, place your custom CSS in a separate file, such as `custom.css`, and reference it in your theme. This approach keeps your customizations isolated, reducing the risk of losing them when your theme is updated.

- **Use Version Control:** If your project involves significant CSS customizations, consider using version control systems like Git. Version control allows you to track changes, collaborate more effectively, and easily revert to previous versions if something goes wrong. It’s especially useful when working on complex or long-term projects.

- **Use Specific Selectors:** To prevent unintended style conflicts, always use specific CSS selectors. This practice helps ensure that your custom styles only apply to the elements you target, avoiding interference with existing theme styles or other customizations.

- **Keep it Organized:** Maintain a well-organized CSS file by using comments to describe sections or specific styles. This makes your code easier to navigate and understand, especially if you or someone else needs to modify or troubleshoot the styles later. Group related styles together and consider following a consistent naming convention for class names.

- **Test Responsiveness:** Custom styles can sometimes affect how your store looks on different devices. After adding or modifying CSS, thoroughly test your store across various screen sizes, including mobile, tablet, and desktop, as well as different browsers, to ensure that your design is responsive and visually appealing everywhere.

## Custom JavaScript

Enhancing your store with custom JavaScript allows you to add dynamic functionality beyond what’s available in the default theme. Whether you're looking to add interactive features, manipulate the DOM, or integrate third-party scripts, custom JavaScript gives you the flexibility to do so.

### Adding Custom Scripts

To add custom JavaScript to your Shopify theme, you need to create or edit JavaScript files directly in the theme's code editor.

#### Creating a Custom JavaScript File

Follow these steps to create and add custom JavaScript to your Shopify theme:

1. **Log in to Shopify Admin:**

   - Visit [shopify.com](https://www.shopify.com) and log in using your store's credentials.

2. **Navigate to the Code Editor:**

   - From the Shopify Admin dashboard, click on **"Online Store"** in the left-hand menu.
   - Under **"Themes"**, find your active theme (marked as "Current Theme") and click on the **"Actions"** dropdown.
   - Select **"Edit code"** from the dropdown menu. This will open the theme code editor, where you can modify the underlying files of your theme.

3. **Add a Custom Javascript File:**

   - In the code editor, locate the **"Assets"** folder in the left-hand sidebar.
   - Click on the **"Add a new asset"** button at the top of the Assets section.
   - In the pop-up window, select **"Create a blank file"** and name it something like `custom.js`. Ensure the file extension is `.js`.
   - Click **"Add asset"** to create the new file. This file will now appear in the Assets folder.

4. **Reference the JavaScript File in the Layout:**

   - Still in the theme code editor, navigate to the **"Layout"** folder and select the `theme.liquid` file.
   - In the `theme.liquid` file, locate the closing `</head>` tag, which is typically near the top of the file.
   - Just before the `</head>` tag or just before the `</body>` tag, add the following code to include your custom JavaScript file:
     ```liquid
     <script src="{{ 'custom.js' | asset_url }}" defer></script>
     ```

5. **Save Your Changes:**

   - After adding your custom Javascript file and referencing it in the `theme.liquid` file, click **"Save"** in the top right corner of the code editor to apply your changes.

### Best Practices

When adding custom JavaScript to your Shopify theme, adhering to best practices ensures that your code is efficient, maintainable, and does not interfere with the performance or functionality of your store.

- **Avoid Overwriting Core Files:** To safeguard your theme from accidental overwrites during updates, avoid directly modifying core theme JavaScript files. Instead, place your custom JavaScript in a separate file, such as `custom.js`, and reference it in your theme. This practice keeps your custom scripts isolated, reducing the risk of losing your customizations when your theme is updated.

- **Use Version Control:** If your project involves significant JavaScript customizations, consider using a version control system like Git. Version control enables you to track changes in your JavaScript code, collaborate with other developers more efficiently, and easily revert to previous versions if issues arise. This is particularly valuable for complex or long-term projects, where maintaining a history of changes and understanding code evolution is crucial.

- **Keep Code Modular:** Organize your JavaScript into smaller, reusable functions or modules. This approach makes your code easier to maintain and debug.

- **Minimize Global Variables:** Limit the use of global variables to avoid conflicts with existing JavaScript in the theme or third-party scripts. Instead, use local variables within functions or use closures to encapsulate your code.

- **Test Across Browsers and Devices:** After implementing custom JavaScript, test your store on various browsers (e.g., Chrome, Firefox, Safari) and devices (e.g., mobile, tablet, desktop) to ensure consistent behavior and appearance.

- **Use Asynchronous Loading:** Load your JavaScript asynchronously using the `defer` or `async` attributes where appropriate. This approach helps prevent scripts from blocking other critical resources, thereby improving page load times.

- **Document Your Code:** Comment your JavaScript code to explain the purpose of specific functions and logic. This practice is particularly helpful for future maintenance and collaboration with other developers.

- **Consider Performance:** Write efficient JavaScript code to avoid negatively impacting your store's performance. Limit the use of large libraries or complex animations that could slow down your site.

## Theme Modifications

Write about customising the theme template and section files and why it is useful or might be used.

### Overview

Liquid is Shopify's templating language, and modifying Liquid files allows you to customize how your store's content is displayed.

- **What is Liquid?**

   - Liquid is a templating language developed by Shopify. It is used to load dynamic content on Shopify storefronts and is the backbone of Shopify theme customization.

- **Basic Syntax:**

   - Example:
    ```liquid
    {% for product in collections.frontpage.products %}
      <h2>{{ product.title }}</h2>
    {% endfor %}
    ```
   - This code loops through products in a collection and displays each product's title.

#### Common Uses <!-- {docsify-ignore} -->

- **Modifying Product Templates:**

   - Add custom fields or change the layout by editing `product.liquid` in the `sections` or `templates` folder.

- **Customizing Collection Pages:**

   - Modify `collection.liquid` to adjust the display of products in a collection, such as changing the grid layout or adding filters.

- **Inserting Dynamic Content:**

   - Use Liquid tags to insert dynamic content such as product recommendations, related blog posts, or promotional banners.

- **Creating New Templates and Sections:**

   - Duplicate an existing Liquid file, rename it, and modify it to create custom page templates that can be selected in the Shopify admin.

### Accessing Files

Write introduction about why and how to access files.

#### Sections

TODO Write Steps for accessing the section files. Follow style from steps for adding custom css via theme editor to re-write the bellow steps:

- **Accessing Section Files:**

   - Navigate to **Online Store** > **Themes** > **Actions** > **Edit code**.
   - Expand Folder Sections
   - Click section to edit

#### Templates

TODO Write Steps for accessing the template files. Follow style from steps for adding custom css via theme editor to re-write the bellow steps:

- **Accessing Section Files:**

   - Navigate to **Online Store** > **Themes** > **Actions** > **Edit code**.
   - Expand Folder Sections
   - Click section to edit

#### Theme

TODO Write Steps for accessing the theme files. Follow style from steps for adding custom css via theme editor to re-write the bellow steps:

- **Accessing Theme Files:**

   - Navigate to **Online Store** > **Themes** > **Actions** > **Edit code**.
   - Expand Folder Sections
   - Click section to edit

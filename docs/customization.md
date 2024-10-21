# Customization

This guide is designed for users who want to go beyond basic theme customization and delve into more advanced modifications. Whether you're adding custom CSS, integrating custom JavaScript, or tweaking Liquid templates, this guide will provide you with the knowledge and best practices to safely and effectively customize your Shopify theme.

## Custom CSS

Customizing your theme’s appearance with CSS allows you to tailor the design to your specific needs, providing a unique look and feel that aligns with your brand. By adding custom CSS, you can make detailed adjustments that aren't always available through the default theme settings, giving you greater control over the visual aspects of your online store.

### Adding Custom Styles

There are a couple of ways you can add custom CSS to your Shopify theme. You can either use the theme editor or directly edit the theme files through the code editor. Both methods allow you to enhance your store's appearance with custom styles.

#### Theme Editor

The Shopify Theme Editor offers a user-friendly interface that allows you to customize your store's appearance without needing to write or edit code directly.

To access and add custom CSS via the Shopify theme editor, follow these steps:

1. **Log in to Shopify Admin:**

   - Visit [shopify.com](https://www.shopify.com) and log in using your store's credentials.

2. **Navigate to Online Store:**

   - From the Shopify Admin dashboard, click on **"Online Store"** in the left-hand menu. This will expand a sub-menu.

3. **Select Themes:**

   - Under **"Online Store"**, click on **"Themes"**. You'll be taken to a page that displays your current theme as well as any other themes you have installed.

4. **Customize the Theme:**

   - On the Themes page, locate your active theme (marked as "Current Theme") and click the **"Customize"** button next to it. This will open the theme editor, where you can modify your theme’s styles and settings.

5. **Locate the Custom CSS Option:**

   - The theme editor offers multiple locations where you can add custom CSS, depending on how broadly or specifically you want the styles to be applied:

   - **Global Custom CSS in Theme Settings:**

     - In the theme editor, scroll down the left-hand sidebar to the **"Theme Settings"** section, typically at the bottom. Here, you might find an option labeled **"Custom CSS"** or **"Additional CSS"**. Adding CSS in this section will apply your styles globally across your entire store, affecting all pages and elements that match the CSS selectors.

   - **Custom CSS for Individual Sections:**

     - Shopify themes often allow you to add custom CSS to specific sections of a page. To do this, click on the section you want to customize (e.g., Header, Footer, Slideshow, Product Grid) in the theme editor sidebar. Look for a **"Custom CSS"** field within the section’s settings. Adding CSS here will apply the styles only to that particular section, allowing for targeted adjustments.

   - **Custom CSS for Specific Templates:**

     - Some Shopify themes allow you to add custom CSS directly to specific page templates (e.g., Product pages, Collection pages, Blog pages). When editing a template in the theme editor, check the sidebar for a **"Custom CSS"** option. This allows you to tailor styles to specific types of pages, providing more granular control over your theme’s appearance.

   - **Custom CSS for Apps and Widgets:**

     - If your store uses third-party apps or widgets, the theme editor may include a **"Custom CSS"** option specifically for these elements. This is usually found in the settings area of the respective app or widget within the theme editor. Adding custom CSS here helps you style app components to better match your store’s overall design.

6. **Add Custom CSS Styles:**

   - Enter your custom CSS styles into the provided field.

7. **Save Your Changes:**

   - Once you’ve added your custom CSS, click **"Save"** to apply the new styles to your theme.

#### Code Editor

To add custom CSS by creating a custom CSS file in the code editor, follow these steps:

1. **Log in to Shopify Admin:**

   - Visit [shopify.com](https://www.shopify.com) and log in using your store's credentials.

2. **Navigate to the Code Editor:**

   - From the Shopify Admin dashboard, click on **"Online Store"** in the left-hand menu.
   - Under **"Themes"**, find your active theme (marked as "Current Theme") and click on the **"Actions"** dropdown.
   - Select **"Edit code"** from the dropdown menu. This will open the code editor, where you can modify the underlying files of your theme.

3. **Add a Custom CSS File:**

   - In the code editor, locate the **"Assets"** folder in the left-hand sidebar.
   - Click on the **"Add a new asset"** button at the top of the Assets section.
   - In the pop-up window, select **"Create a blank file"** and name it something like `custom.css`. Ensure the file extension is `.css`.
   - Click **"Add asset"** to create the new file. This file will now appear in the Assets folder.

4. **Reference the CSS File in Your Theme:**

   - Still in the code editor, navigate to the **"Layout"** folder and select the `theme.liquid` file.
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

#### Code Editor

Follow these steps to create and add custom JavaScript to your Shopify theme:

1. **Log in to Shopify Admin:**

   - Visit [shopify.com](https://www.shopify.com) and log in using your store's credentials.

2. **Navigate to the Code Editor:**

   - From the Shopify Admin dashboard, click on **"Online Store"** in the left-hand menu.
   - Under **"Themes"**, find your active theme (marked as "Current Theme") and click on the **"Actions"** dropdown.
   - Select **"Edit code"** from the dropdown menu. This will open the code editor, where you can modify the underlying files of your theme.

3. **Add a Custom Javascript File:**

   - In the code editor, locate the **"Assets"** folder in the left-hand sidebar.
   - Click on the **"Add a new asset"** button at the top of the Assets section.
   - In the pop-up window, select **"Create a blank file"** and name it something like `custom.js`. Ensure the file extension is `.js`.
   - Click **"Add asset"** to create the new file. This file will now appear in the Assets folder.

4. **Reference the JavaScript File in the Layout:**

   - Still in the code editor, navigate to the **"Layout"** folder and select the `theme.liquid` file.
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

Making modifications to theme template files allows you to tailor your store’s design and functionality to better suit your brand and business needs. By customizing the theme’s Liquid files, you can control how content is displayed, add unique features, and create a more personalized shopping experience for your customers.

### Overview

Liquid is Shopify's powerful templating language, designed to load dynamic content and provide the flexibility needed to create a unique storefront. Whether you want to alter how products are displayed, add new sections to your homepage, or insert dynamic content, understanding and utilizing Liquid is key to unlocking the full potential of your Shopify theme.

- **What is Liquid?**

   - Liquid is a templating language developed by Shopify, enabling you to load dynamic content on your storefront. It serves as the foundation for all Shopify theme customization, allowing you to control everything from basic layout adjustments to complex, data-driven displays.

- **Basic Syntax:**

   - Example:
    ```liquid
    {% for product in collections.frontpage.products %}
      <h2>{{ product.title }}</h2>
    {% endfor %}
    ```
   - This example loops through products in a specific collection (in this case, the "frontpage" collection) and displays each product's title.

#### Common Uses <!-- {docsify-ignore} -->

- **Modifying Product Templates:**

   - Customize how product information is presented by editing the `product.liquid` file within the `sections` or `templates` folder. You can add custom fields, rearrange the layout, or incorporate new elements such as badges or custom buttons.

- **Customizing Collection Pages:**

   - Adjust the appearance of product collections by modifying the `collection.liquid` file. This might involve changing the grid layout, adding filtering options, or incorporating dynamic content like banners or promotions.

- **Inserting Dynamic Content:**

   - Use Liquid tags to include dynamic content, such as product recommendations, related blog posts, or promotional banners that update automatically based on the products being viewed.

- **Creating New Templates and Sections:**

   - To create custom page templates, duplicate an existing Liquid file, rename it, and modify it to suit your needs. These custom templates can then be selected within the Shopify admin when creating or editing pages.

### Accessing Files

To make any modifications to your theme’s Liquid files, you need to access the theme’s code editor within the Shopify admin. This is where all of your theme’s files, including templates and sections, are stored and can be edited.

#### Sections

Section files control specific components of your theme, such as headers, footers, and product grids. Modifying these files allows you to adjust the layout and functionality of individual parts of your store.

1. **Log in to Shopify Admin:**

   - Visit [shopify.com](https://www.shopify.com) and log in using your store's credentials.

2. **Navigate to the Code Editor:**

   - From the Shopify Admin dashboard, click on **"Online Store"** in the left-hand menu.
   - Under **"Themes"**, find your active theme (marked as "Current Theme") and click on the **"Actions"** dropdown.
   - Select **"Edit code"** from the dropdown menu. This will open the code editor, where you can modify the underlying files of your theme.

3. **Open the Sections Folder:**

   - In the code editor, locate the **Sections** folder in the left-hand sidebar.

4. **Edit the Desired Section:**

   - Click on the section file you want to edit. The file will open in the code editor where you can make your changes.

#### Templates

Template files define the overall layout and structure of different types of pages, such as product pages, collection pages, and blog posts. Editing these files allows you to customize how entire pages are displayed.

1. **Log in to Shopify Admin:**

   - Visit [shopify.com](https://www.shopify.com) and log in using your store's credentials.

2. **Navigate to the Code Editor:**

   - From the Shopify Admin dashboard, click on **"Online Store"** in the left-hand menu.
   - Under **"Themes"**, find your active theme (marked as "Current Theme") and click on the **"Actions"** dropdown.
   - Select **"Edit code"** from the dropdown menu. This will open the code editor, where you can modify the underlying files of your theme.

3. **Open the Templates Folder:**

   - In the code editor, locate the **Templates** folder in the left-hand sidebar.

4. **Edit the Desired Template:**

   - Click on the template file you wish to edit. The file will open in the code editor, allowing you to modify the page layout and structure.

#### Layout

The main layout files control the overall settings and functions of your theme. Customizing these files can impact the entire store.

1. **Log in to Shopify Admin:**

   - Visit [shopify.com](https://www.shopify.com) and log in using your store's credentials.

2. **Navigate to the Code Editor:**

   - From the Shopify Admin dashboard, click on **"Online Store"** in the left-hand menu.
   - Under **"Themes"**, find your active theme (marked as "Current Theme") and click on the **"Actions"** dropdown.
   - Select **"Edit code"** from the dropdown menu. This will open the code editor, where you can modify the underlying files of your theme.

2. **Open the Layout Folder:**

   - In the code editor, locate the **Layout** or **Config** folder in the left-hand sidebar, depending on what you need to edit.

3. **Edit the Desired Layout:**

   - Click on the layout file you want to edit, such as `theme.liquid`. This file will open in the code editor where you can make necessary changes to the global layout.

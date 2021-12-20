# [Import Multilingual Websites Using WP All Import and WPML - WPML](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/)

WP All Import plugin allows you to import posts, pages, WooCommerce products, and other custom post types in bulk from CSV files. You can also import content in multiple languages.

## On This Page[](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#on-this-page)

**How to import your multilingual content**:

-   [Before Importing](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#before-importing)
-   [Prepare Your CSV Files for Importing](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#how-to-prepare-csv-xml-files)
-   [Create Your Taxonomies in WordPress](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#importing-posts-with-taxonomies)
-   [How To Import Posts](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#How-To-Import-Posts)
-   [How To Import WooCommerce Products](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#How-To-Import-WooCommerce-Products)

**This article also covers:**

-   [Exporting Posts](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#importing-posts-from-an-old-wordpress-installation)
-   [Importing a Custom Database Design Into WordPress](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#do-you-want-to-import-a-custom-database-design-into-wordpress)
-   [Known Issues with WPML All Import](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#known-issues)
-   [Getting Help](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#getting-help)

## Getting Started[](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#getting-started)

Start by installing and activating the following plugins:

-   [WP All Import plugin](https://wordpress.org/plugins/wp-all-import/)
-   WPML core plugin
-   WPML All Import add-on (available from your [WPML Downloads](https://wpml.org/account/downloads/) page)

If you want to import WooCommerce products, you will also need [WooCommerce Import Add-On Pro](https://www.wpallimport.com/woocommerce-product-import/).

New to WPML? Check out our [Getting Started Guide](https://wpml.org/documentation/getting-started-guide/). It quickly walks you through different translation options you can use.

## Before Importing[](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#before-importing)

Before you start with any importing, go to **WP All Import → Manage Imports** and disable the option **Increase speed by disabling do\_action calls in wp\_insert\_post during import**.

This is very important because having this option enabled while running your imports might cause issues.

## Prepare Your CSV Files for Importing[](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#how-to-prepare-csv-xml-files)

Create a spreadsheet to contain your default language post titles and content, and save it as a CSV file. Give it a meaningful filename, as this will help identify the file from a list later in the process:

[![Sample default language CSV prepared for importing](https://cdn.wpml.org/wp-content/uploads/2020/09/english-csv-1-1024x252.png)](https://cdn.wpml.org/wp-content/uploads/2020/09/english-csv-1.png)

Sample default language CSV prepared for importing

Prepare separate spreadsheets for each additional language:

[![Sample separate CSV file in a secondary language](https://cdn.wpml.org/wp-content/uploads/2020/09/polish-csv-1024x217.png)](https://cdn.wpml.org/wp-content/uploads/2020/09/polish-csv.png)

Sample additional language CSV prepared for importing

### Add a Unique Identifier[](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#Add-a-Unique-Identifier)

When you import the files later, WP All Import will need a way to match the default language posts to their corresponding translations in the other files.

To do this, you need to specify a **unique identifier** for each post. Assign an ID number to one of your posts in your default language. Then, use that same ID number for the same post in your secondary language files. By looking at this ID, you can tell which post is the translation of another by finding the same ID number in your files.

For example, in the screenshots above, you can see that, “Hello World!” has a Polish translation of “Witaj świecie!” because they have the same unique identifier.

## Create Your Taxonomies in WordPress[](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#importing-posts-with-taxonomies)

If you are importing translated posts with taxonomies (categories, tags, or custom taxonomies), **you must create the exact same taxonomies in your WordPress site before importing the post files**. This can be done in two ways:

1.  Create the terms manually and [translate them](https://wpml.org/documentation/getting-started-guide/translating-post-categories-and-custom-taxonomies/). Make sure the terms that you create in both your default and secondary languages match the terms you use in your CSV files exactly. If you have a lot of terms to translate, you can check our guide on [translating all taxonomy terms at once.](https://wpml.org/faq/how-to-translate-all-taxonomy-terms-at-once/)
2.  Import the terms using WP All Import. To do this, prepare new CSV files to import the taxonomies and their translations. Add the unique identifier column to all CSV files to link each taxonomy term with its translation. You can follow WP All Import’s guide on [importing taxonomies](https://www.wpallimport.com/documentation/taxonomies/overview/), but be sure to set the import language as described in the [section later in this article.](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#How-To-Import-Posts)

Each time you import posts with taxonomies, **you need to create the taxonomy terms first**, then import the posts. Once the taxonomy terms and translations exist and match the terms in your CSV file, WP Import will be able to set the correct taxonomy for posts you import.

### Matching Taxonomy Translations After Import[](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#Matching-Taxonomy-Translations-After-Import)

As previously stated, we highly recommend creating your taxonomy terms and translations **before** importing your CSV files. If you do not create your taxonomies before importing your CSV files, your secondary language taxonomy terms will not be connected as translations of the default language terms. You will need to edit each of your translated taxonomy terms to match them with the correct default language taxonomy term.  
To do this:

1.  Go to **Posts → Categories** (or whichever taxonomy type you are correcting).
2.  Switch to your secondary language using the language switcher at the top of the page.
3.  Edit the taxonomy term you need to fix.

[![Editing a taxonomy term in a secondary language](https://cdn.wpml.org/wp-content/uploads/2020/09/editing-taxonomy-in-secondary-language-1024x455.png)](https://cdn.wpml.org/wp-content/uploads/2020/09/editing-taxonomy-in-secondary-language.png)

Editing a taxonomy term in a secondary language

4.  At the bottom of the page, choose which default language taxonomy term the current term is a translation of.

[![Mapping a translated taxonomy term to its default language value](https://cdn.wpml.org/wp-content/uploads/2020/09/mapping-translated-taxonomy.png)](https://cdn.wpml.org/wp-content/uploads/2020/09/mapping-translated-taxonomy.png)

Mapping a translated taxonomy term to its default language value

## How To Import Posts[](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#How-To-Import-Posts)

Once your taxonomies and their translations are in place, you are ready to import your CSV files. Be sure to import your default language files first, followed by your secondary language files. We will summarize the steps below. For more detailed documentation, please see WP All Import’s article on [how to import files](https://www.wpallimport.com/documentation/getting-started/importing-an-xml-or-csv-file/).

### First, Import the Default Language File[](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#first-import-the-default-language-file)

To import your default language file:

1.  Go to **WP All Import → New Import**, and click **Upload a file** to upload your default language CSV file. Choose whether you are uploading new or existing items, and what type of element you are importing.
2.  On the next screen, you can review each row in your CSV file. If it all looks correct, click **Continue to Step 3**.
3.  Map your column titles from the right sidebar to the correct fields by dragging and dropping them. Expand the **WPML All Import** metabox and choose your default language. Then, click **Continue to Step 4**.

[![Mapping the default language fields in the WP All Import wizard](https://cdn.wpml.org/wp-content/uploads/2020/09/mapping-import-fields-993x1024.png)](https://cdn.wpml.org/wp-content/uploads/2020/09/mapping-import-fields.png)

Mapping the default language fields in the WP All Import wizard

4.  Map the unique identifier to the correct element in your CSV or XML file. Click **Continue** to view a summary of your import, then click **Confirm & Run Import** to import your default language posts.

[![Setting the unique identifier value](https://cdn.wpml.org/wp-content/uploads/2020/09/setting-unique-identifier-1024x795.png)](https://cdn.wpml.org/wp-content/uploads/2020/09/setting-unique-identifier.png)

Setting the unique identifier value

### Next, Import the Secondary Language File[](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#next-import-the-secondary-language-file)

Repeat the import process with your secondary language file with a few exceptions:

1.  In the **WPML All Import** metabox, choose the correct secondary language.
2.  Expand the **Automatic Record Matching to Translate** section and select the file that you used to import the default language posts.
3.  Drag the field that you are using as the unique identifier to the **Unique Identifier** field. This field and the **Unique Identifier** field on the next screen needs to be the same as the one you chose during the default language import.

[![Setting the secondary language, parent import, and unique identifier](https://cdn.wpml.org/wp-content/uploads/2020/09/mapping-secondary-language-fields.png)](https://cdn.wpml.org/wp-content/uploads/2020/09/mapping-secondary-language-fields.png)

Setting the secondary language, parent import, and unique identifier

[![Setting the same unique identifier for the secondary language](https://cdn.wpml.org/wp-content/uploads/2020/09/setting-unique-identifier-secondary-language-1024x788.png)](https://cdn.wpml.org/wp-content/uploads/2020/09/setting-unique-identifier-secondary-language.png)

Setting the same unique identifier for the secondary language

This import will create posts in secondary languages and connect them as the translations of the default language.

### Adding Translations When the Default Language Content Already Exists on the Site[](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#Adding-Translations-When-the-Default-Language-Content-Already-Exists-on-the-Site)

Because WP All Import relies on the unique identifier to connect translated posts with their corresponding default language post, you cannot upload the secondary language file to add translations to pre-existing default language content. If you do this, WP All Import will not know which posts the translations belong to.

To add translations when default language content already exists on the site:

1.  Export your default language content using [WP All Export](https://www.wpallimport.com/documentation/quickstart/export/).
2.  Edit the newly created CSV to add a column for the unique identifier.
3.  Delete the original content from the site.
4.  [Import the default language CSV file](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#how-to-import-posts) with the unique identifier column. Make sure to import it as **New items**.

Once the default language file has been imported, you can continue with your secondary language file [as previously explained](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#next-import-the-secondary-language-file).

## How To Import WooCommerce Products[](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#How-To-Import-WooCommerce-Products)

[WooCommerce Import Add-On Pro](https://www.wpallimport.com/woocommerce-product-import/) is required for importing simple and variable WooCommerce products. Once you have purchased WP All Import, you can find the link to download WooCommerce Import Add-On Pro on your WP All Import downloads page.

You can import WooCommerce simple products by following the process described above for [creating taxonomies](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#importing-posts-with-taxonomies) and [importing posts](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#how-to-import-posts).

If you need to import WooCommerce variable products, there are some additional steps. Follow WP All Import’s tutorial for instructions on [how to import variable WooCommmerce products](http://www.wpallimport.com/documentation/woocommerce/variable-products/). Don’t forget to add the unique identifier column!

You can then import your translations the same way, paying close attention to the extra considerations as outlined in the tutorial. Be sure to create all your product taxonomy terms and translations before importing your CSV files.

### How To Manually Import Products With Prices in Other Currencies[](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#how-to-manually-import-products-with-set-prices-for-other-currencies)

To import products with manually set prices for other currencies, make sure to set the relevant fields in the **WooCommerce Add-On** section for the default language import. This includes the regular price and sale price.

[![](https://cdn.wpml.org/wp-content/uploads/2019/11/Setting-the-WooCommerce-import-fields.png)](https://cdn.wpml.org/wp-content/uploads/2019/11/Setting-the-WooCommerce-import-fields.png)

Setting the WooCommerce import fields

You also need to add the following custom fields in the default language import in order for the prices to show correctly on the product pages in secondary languages. In our example, we have manually set prices for products in Euros. Hence, we have added the following custom fields:

-   `_regular_price_EUR`
-   `_sale_price_EUR`
-   `_price_EUR`
-   `_sale_price_dates_to_EUR`
-   `_sale_price_dates_from_EUR`
-   `_wcml_schedule_EUR`
-   `_wcml_custom_prices_status`

[![](https://cdn.wpml.org/wp-content/uploads/2019/11/Setting-the-custom-fields.png)](https://cdn.wpml.org/wp-content/uploads/2019/11/Setting-the-custom-fields.png)

Adding the custom fields

Depending on the currency you have set prices for, you need to change the suffix of several of the custom fields to match the currency code. To get the currency code:

1.  Go to **WooCommerce → WooCommerce Multilingual**.
2.  Go to the **Multi-currency** tab and click on the **Add currency** button.
3.  Select the currency to get its code.

[![](https://cdn.wpml.org/wp-content/uploads/2019/11/Getting-the-currency-suffix.png)](https://cdn.wpml.org/wp-content/uploads/2019/11/Getting-the-currency-suffix.png)

Getting the currency code

If you are importing products in more than one language and they all have manually set prices for all other currencies, make sure to add custom fields associated with all the currency suffixes.

## Exporting Posts[](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#importing-posts-from-an-old-wordpress-installation)

WPML and WP All Import do not have an option to export posts from a WordPress installation.

We do **not** recommend using the standard WordPress option to export content to XML files (**Tools → Export**). You will have to split those files into many (one for each language) and add an XML element with a Translation Group ID. XML files are not easy to edit, so it can be a lengthy process.

If you want to save a backup of your posts, we recommend using an export plugin like [WP All Export](https://wpml.org/documentation/plugins-compatibility/export-multilingual-websites-using-wp-all-export-wpml/). These plugins export CSV files, which make it easier to split files per language and add information about the Translation Group ID.

You can do this manually, or if you are a programmer, you can parse those files in PHP. For every row, you can check the translation of the given post using the [**wpml\_object\_id** filter](https://wpml.org/wpml-hook/wpml_object_id/).

## Importing a Custom Database Design Into WordPress[](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#do-you-want-to-import-a-custom-database-design-into-wordpress)

Migrating from a custom database with different tables into WordPress can be a challenging task. Fortunately, you can accomplish this using [Toolset plugins](https://toolset.com/) and WP All Import. Check Toolset’s guide on [importing a database into WordPress](https://toolset.com/documentation/programmer-reference/how-to-import-a-database-into-wordpress/). The video below illustrates the migration process in details:

<iframe frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" src="https://www.youtube.com/embed/2PIChT5T0oQ?rel=0&amp;toolset=1&amp;enablejsapi=1&amp;origin=https%3A%2F%2Fwpml.org" data-gtm-yt-inspected-9980035_20="true" id="107929950"></iframe>

## Known Issues[](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#known-issues)

There are no known compatibility issues between this plugin and WPML.

## Getting Help[](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/#getting-help)

If you need help using WPML All Import, visit [WPML’s support forum](https://wpml.org/forums/forum/english-support/).
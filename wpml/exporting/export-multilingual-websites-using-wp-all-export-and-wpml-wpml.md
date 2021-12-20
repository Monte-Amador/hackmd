# [Export Multilingual Websites Using WP All Export and WPML - WPML](https://wpml.org/documentation/plugins-compatibility/export-multilingual-websites-using-wp-all-export-wpml/#Known-Issues)

WP All Export allows you to export multilingual websites translated with WPML. You can export posts, pages, WooCommerce products, custom post types, taxonomies, and more.

## On This Page[](https://wpml.org/documentation/plugins-compatibility/export-multilingual-websites-using-wp-all-export-wpml/#on-this-page)

-   [Getting Started](https://wpml.org/documentation/plugins-compatibility/export-multilingual-websites-using-wp-all-export-wpml/#getting-started)
-   [Exporting Multilingual Websites](https://wpml.org/documentation/plugins-compatibility/export-multilingual-websites-using-wp-all-export-wpml/#Exporting-Multilingual-Websites)
-   [Exporting Your Multilingual Content With a Cron Job](https://wpml.org/documentation/plugins-compatibility/export-multilingual-websites-using-wp-all-export-wpml/#Exporting-Your-Multilingual-Content-With-a-Cron-Job)
-   [Known Issues with WP All Export](https://wpml.org/documentation/plugins-compatibility/export-multilingual-websites-using-wp-all-export-wpml/#Known-Issues)
-   [Importing Your Multilingual Posts and Pages](https://wpml.org/documentation/plugins-compatibility/export-multilingual-websites-using-wp-all-export-wpml/#Importing-Your-Multilingual-Posts-and-Pages)

## Getting Started[](https://wpml.org/documentation/plugins-compatibility/export-multilingual-websites-using-wp-all-export-wpml/#getting-started)

Start by installing and activating the following plugins:

-   [WP All Export](http://www.wpallimport.com/export/) plugin
-   WPML core plugin and WPML String Translation add-on
-   For certain types of content like ACF and WooCommerce, you might need [additional add-ons](https://www.wpallimport.com/some-wp-all-export-functionality-is-moving-to-add-ons/)

## Exporting Multilingual Websites[](https://wpml.org/documentation/plugins-compatibility/export-multilingual-websites-using-wp-all-export-wpml/#Exporting-Multilingual-Websites)

With a multilingual website, to export your content in all languages you will need to export the data for each content type and each language separately. For example, if you have translated your pages and posts from English to French using the WPML plugin and wish to export the data, you will end up with four files:

-   English Posts
-   French Posts
-   English Pages
-   French Pages

When exporting the files, you will need to have a field that links each page or post to its corresponding translated page or post. This can be accomplished by simply adding a field called **WPML Translation ID** to your files.

Let’s go over a quick example of how we can export the posts for a multilingual website.

1.  To export the default language posts, go to WP **All Export** → **New Export**.
2.  Choose Posts from the **Choose a Post Type** drop-down menu.
3.  Click on the **Customize Export File** button.

[![](https://cdn.wpml.org/wp-content/uploads/2021/08/wpml-wp-all-export-select-post-type-1.png)](https://cdn.wpml.org/wp-content/uploads/2021/08/wpml-wp-all-export-select-post-type-1.png)

Choosing the post type you want to export

4.  Expand the **Standard** section under the **Available Data** window, and drag the **WPML Translation ID** to the fields area.
5.  You can also add the **Categories** and **Tags** fields to be exported.

[![](https://cdn.wpml.org/wp-content/uploads/2016/08/Adding-the-WPML-translation-ID-categories-and-tags-to-the-exported-file-2.gif)](https://cdn.wpml.org/wp-content/uploads/2016/08/Adding-the-WPML-translation-ID-categories-and-tags-to-the-exported-file-2.gif)

Adding which fields should be exported

6.  If you’re running the free version of WP All Export, expand the **Advanced Options** section. If you’re running the pro version of WP All Export, expand the **WPML** section instead. In either case, choose your site’s default language, and click the **Continue** button.

[![](https://cdn.wpml.org/wp-content/uploads/2021/08/wpml-wp-all-export-advanced-options.png)](https://cdn.wpml.org/wp-content/uploads/2021/08/wpml-wp-all-export-advanced-options.png)

Exporting the default language posts

7.  On the **Configure Advanced Settings** screen, choose your preferred settings then add the exported file name in the **Friendly Name** field. You can then click on the **Confirm & Run Export**.

[![](https://cdn.wpml.org/wp-content/uploads/2016/08/Name-your-file-and-run-the-export-1024x682.png)](https://cdn.wpml.org/wp-content/uploads/2016/08/Name-your-file-and-run-the-export.png)

Naming your file and running the export

8.  Once the export process is completed, click on the **CSV** button to download the exported file.

[![](https://cdn.wpml.org/wp-content/uploads/2016/08/Download-the-CSV-file-1024x536.png)](https://cdn.wpml.org/wp-content/uploads/2016/08/Download-the-CSV-file.png)

Downloading the CSV file

9.  Now we can open the CSV file and see the **WPML Translation ID** field, which will connect both the default and the secondary language CSV files when importing the data.

[![](https://cdn.wpml.org/wp-content/uploads/2016/08/Exported-default-language-CSV-file-1024x667.png)](https://cdn.wpml.org/wp-content/uploads/2016/08/Exported-default-language-CSV-file.png)

Exported default language CSV file

10.  Repeat the same process, but this time make sure to choose the secondary language you want to export**.**

[![](https://cdn.wpml.org/wp-content/uploads/2016/08/Choose-the-secondary-language-you-want-to-export.png)](https://cdn.wpml.org/wp-content/uploads/2016/08/Choose-the-secondary-language-you-want-to-export.png)

Choosing the secondary language you want to export

## Exporting Your Multilingual Content With a Cron Job[](https://wpml.org/documentation/plugins-compatibility/export-multilingual-websites-using-wp-all-export-wpml/#Exporting-Your-Multilingual-Content-With-a-Cron-Job)

When running a [WordPress cron job](https://codex.wordpress.org/Function_Reference/wp_cron) to export your multilingual content, you may find that the content ends up assigned to the default language. To avoid this, you need to add the language code to the cron job’s URL. This way, the export is done in the correct language.

For example, to export the data in Portuguese, we can use the following URLs:

-   http://example.com/pt-pt/wp-cron.php?export\_key=qj3Y0NoTYgS7&export\_id=52&action=trigger
-   http://example.com/pt-pt/wp-cron.php?export\_key=qj3Y0NoTYgS7&export\_id=52&action=processing

As you can see, we added the **/pt-pt/** (language code for Portuguese) to the URLs.

## Known Issues[](https://wpml.org/documentation/plugins-compatibility/export-multilingual-websites-using-wp-all-export-wpml/#known-issues)

There are no known compatibility issues between this plugin and WPML.

## Importing Your Multilingual Posts and Pages[](https://wpml.org/documentation/plugins-compatibility/export-multilingual-websites-using-wp-all-export-wpml/#Importing-Your-Multilingual-Posts-and-Pages)

In this tutorial, we have provided detailed instructions on how to export your multilingual posts and pages. To import your multilingual posts and pages, you can follow the detailed steps given in the [WP All Import documentation](https://wpml.org/documentation/related-projects/wpml-all-import-plugin-website-import-with-wpml/).
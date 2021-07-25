# General Wordpress Development Overview

## Overview WP
1. Develop using php 7.4
3. Use [ Underscores ](https://underscores.me/) as the starter theme or if using webpack https://github.com/carrieforde/_s-with-webpack
4. Use https://developer.wordpress.org/reference/functions/get_template_part/ and pass in the $ARGS to Remain DRY.
6. Develop locally (i recommend "flywheel local" https://localwp.com/ ) deploy to a NOFOLLOW staging url.
8. All text to be wrapped in either p, li or h1 to h3 tag. Dont use divs to wrap text. use div for layout.

### WordPress Setup
1. Choose a unique relavent username(not admin) for the main login username, ensure it is stong.
2. Use stong password, store in lastpass and nowhere else.
3. Ensure your local and staging site is set to no-follow

## Components
1. Ensure banners and blog posts and all other components that use an image has a default image incase the image is not entered in the admin.
2. When we create 'post cards' ensure the whole card is clickable not just the "read more" link.

## Images
1. Create [ custom image sizes ](https://developer.wordpress.org/reference/functions/add_image_size/) for all components that use images. Do not load small photos into the media library. Always load large imagery into the media library and code the component to use a custom image size. Remember to run https://wordpress.org/plugins/regenerate-thumbnails/ or you custom image will not work.
2. Always rename imagery to a simple "memorable and searchable" name before loading the image into the media library.
3. use a srcset to output responsive images on the frontend for all responsive break points. see design seciton. https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images Please keep this inmind when choosing slideshow plugins https://www.metaslider.com/image-slide-demo/. the slideshows are to also utilise srcset
4. Use svg for icons, images and logos where posible. We do not use fontawesome as its too bloated.

## Wordpress Menus
1. Construct wordpress menus using pages. Not custom links. Create the page if it does not exist.

## Shortcodes
1. Do not create custom shortcodes. Our preference is to build blocks instead of shortcodes. Please discuss before creating any custom shortcodes.

## Plugins
Firstly, try not to use a plugin if you dont have to. Consult with Senior dev if your tempted to use a plugin before installing the plugin.

7. Use Query Monitor as you develop, it will let you know of any errors; 

### PXS Commonly used Premium Plugins
 
1. Advanced Custom Fields Pro
1. Gravity Forms
2. Duplicate Post
3. Updraft
4. Yoast
5. Woocommerce
6. db-migrate
7. query-monitor for local sites only

## Recommended file structures 
### Using Webpack https://carrieforde.com/webpack-wordpress/ install
```
theme /
├── 404.php
├── LICENSE
├── README.md
├── acf-json
├── archive.php
├── comments.php
├── footer.php
├── functions.php
├── header.php
├── inc
    ├── acf.php
    ├── template-functions.php
    ├── template-tags.php
├── index.php
├── layouts
├── node_modules
├── package-lock.json
├── package.json
├── page.php
├── phpcs.xml.dist
├── public
├── screenshot.png
├── search.php
├── sidebar.php
├── single.php
├── src
    ├── images
    ├── index.js
    ├── js
    ├── libs
    └── sass
         ├── _normalize.scss
         ├── _slick-carousel.scss
         ├── _slick-dots.scss
         ├── blocks
         │   ├── _accordion.scss
         │   ├── _articles.scss
         │   ├── _blocks.scss
         │   ├── _box-slider.scss
         │   ├── _buttons.scss
         │   ├── _columns.scss
         │   └── includes
         │       ├── _featured-post.scss
         │       ├── _location-filters.scss
         │       ├── _post-filters.scss
         │       └── _post-meta.scss
         ├── elements
         │   ├── _elements.scss
         │   ├── _lists.scss
         │   └── _tables.scss
         ├── forms
         │   ├── _buttons.scss
         │   ├── _fields.scss
         │   ├── _forms.scss
         │   ├── _messages.scss
         │   ├── _post-filters.scss
         │   └── _select.scss
         ├── layout
         │   ├── _content-sidebar.scss
         │   ├── _no-sidebar.scss
         │   └── _sidebar-content.scss
         ├── media
         │   ├── _captions.scss
         │   ├── _galleries.scss
         │   └── _media.scss
         ├── mixins
         │   └── _mixins-master.scss
         ├── modules
         │   ├── _accessibility.scss
         │   ├── _alignments.scss
         │   ├── _clearings.scss
         │   └── _infinite-scroll.scss
         ├── navigation
         │   ├── _breadcrumbs.scss
         │   ├── _main.scss
         │   ├── _mixins.scss
         │   ├── _mobile.scss
         │   ├── _navigation.scss
         │   ├── _pagination.scss
         │   └── _utility.scss
         ├── site
         │   ├── _editor.scss
         │   ├── _site.scss
         │   ├── primary
         │   │   ├── _comments.scss
         │   │   ├── _footer.scss
         │   │   ├── _header.scss
         │   │   └── _posts-and-pages.scss
         │   └── secondary
         │       └── _widgets.scss
         ├── style.scss
         ├── typography
         │   ├── _copy.scss
         │   ├── _headings.scss
         │   └── _typography.scss
         └── variables-site
             ├── _colors.scss
             ├── _columns.scss
             ├── _structure.scss
             ├── _typography.scss
             └── _variables-site.scss
├── style-editor.css
├── style.css
├── template-parts
    ├── block
    ├── content-accordion.php
        ├── content-articles.php
        ├── content-box-slider.php
        ├── content-contact-form.php
        ├── content-cta-with-form.php
        ├── content-featured-post.php
    ├── content-news.php
    ├── content-none.php
    ├── content-page-header.php
    ├── content-page.php
    ├── content-post.php
    ├── content-postcard.php
    ├── content-postmeta.php
    ├── content-search.php
    ├── content.php
    └── includes
├── webpack.config.js
└── woocommerce.css
```
### Alternative file stucture using grunt
```
├── 404.php
├── LICENSE
├── README.md
├── acf-json
├── archive-project.php
├── archive.php
├── comments.php
├── composer.json
├── composer.lock
├── css
   ├── fancybox
   └── select2
├── dev
    ├── Gruntfile.js
    ├── js
    ├── node_modules
    ├── package-lock.json
    ├── package.json
    └── sass
├── fonts
├── footer.php
├── front-page.php
├── functions.php
├── header.php
├── home.php
├── images
├── inc
    ├── acf.php
    ├── custom-header.php
    ├── customizer.php
    ├── jetpack.php
    ├── template-functions.php
    ├── template-tags.php
    └── woocommerce.php
├── index.php
├── js
├── languages
├── package.json
├── page.php
├── phpcs.xml.dist
├── readme.txt
├── screenshot.png
├── search.php
├── sidebar.php
├── single-product.php
├── single-project.php
├── single.php
├── style-rtl.css
├── style.css
├── template-parts
├── vendor
└── woocommerce
```

 ### Adhere to WordPress best practices broadly defined here:

http://codex.wordpress.org/working_with_wordpress  http://codex.wordpress.org/developer_documentation  

1. Follow the wordpress coding standards.  http://codex.wordpress.org/wordpress_coding_standards

1. Data must be validated and sanitized on input and escaped on output.

1. Avoid direct calls to php scripts in your theme and do not try to load the wordpress environment on your own.

1. Ensure code will be both backward-compatible and future-proof using the wordpress core apis.

1. Encapsulate all code within a theme and plugins – do not scatter scripts or other assets in other locations.

1. Use standard wordpress theme development practices. avoid overriding the native theming engine with a third party engine (e.g. mustache or smarty) or an unusual framework.

1. Avoid modifying the server side page rendering based on visitor or other one off properties for unauthenticated visitors (this is imperative in environments with page caching enabled).

1. Avoid interacting with cookies on the server side. client side interaction (javascript) is fine.

1. Avoid direct interaction with database tables (sql queries). strongly avoid scripts that alter the database structure by, for example, adding or altering database fields, and creating new tables.

1. Clean up after yourself: remove unused files and directories and any unused code fragments or debugging comments.

1. Adhere to a consistent coding style.

*under no circumstances should you ever edit wordpress core files or plugin files directly. 
if you need to modify a plugin, hook from the theme’s functions.php file or create a custom plugin.

### Database

Avoid direct interaction with database tables (SQL queries). 
In reality, 9 out of 10 times, the same result can be accomplished by using an official WordPress function or API, which often include sophisticated caching while ensuring forwards compatibility.

Strongly avoid scripts that alter the database structure by, for example, adding or altering database fields, and creating new tables. In most cases, WordPress’s sophisticated custom post types, taxonomies, options, and meta data API’s can accomplish the same result with superior security and performance (especially in cache-enabled environments). Scripts that alter the database structure require dramatically more time to audit, review, and test.

In the event that database interaction is truly essential, WordPress provides a class of functions for all database manipulations. The class is called wpdb and is loosely based on the ezSQL class written and maintained by Justin Vincent.

Learn more about the $wpdb Object: http://codex.wordpress.org/Class_Reference/wpdb

### Validation and Sanitization

#### Input Validation
To validate is to ensure the data you’ve requested of the user matches what they’ve submitted. There are several core methods you can use for input validation; usage obviously depends on the type of fields you’d like to validate.
More
information:http://codex.wordpress.org/Validating_Sanitizing_and_Escaping_User_Data#Validating:_Checki ng_User_Input

#### Escape Output
For security on the other end of the spectrum, we have escaping. To escape is to take the data you may already have and help secure it prior to rendering it for the end user.
More information: http://codex.wordpress.org/Validating_Sanitizing_and_Escaping_User_Data#Escaping:_Securing_Output

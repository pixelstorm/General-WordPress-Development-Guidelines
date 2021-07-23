# General Wordpress Development Overview

## Overview WP
1. Develop using php 7.4
2. Commit your theme development to PixelStorm beanstalk repo
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

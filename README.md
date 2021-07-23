Wordpress Development Overview
Develop using php 7.4
Use our git flow proceedure
Use Underscores as the starter theme or if using webpack https://github.com/carrieforde/_s-with-webpack
Use https://developer.wordpress.org/reference/functions/get_template_part/ and pass in the $ARGS to Remain DRY.
Use svg for icons, images and logos where posible. We do not use fontawesome as its too bloated.
Develop locally (i recommend "flywheel local" https://localwp.com/ ) deploy to a NOFOLLOW staging url.
Use Query Monitor as you develop, it will let you know of any errors;
All text to be wrapped in either p, li or h1 to h3 tag. dont use divs to wrap text. use div for layout.
When we create 'post cards' ensure the whole card is clickable not just the "read more" link.
Create custom image sizes for all components that use images. Do not load small photos into the media library. Always load large imagery into the media library and code the component to use a custom image size. Remember to run https://wordpress.org/plugins/regenerate-thumbnails/ or you custom image will not work.
Always rename imagery to a simple "memorable and searchable" name before loading the image into the media library.
use a srcset to output responsive images on the frontend for all responsive break points. see design seciton. https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images Please keep this inmind when choosing slideshow plugins https://www.metaslider.com/image-slide-demo/. the slideshows are to also utilise srcset
Constuct wordpress menus using pages. not custom links. Create the page if it does not exist.

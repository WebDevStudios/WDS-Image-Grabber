# WDS Image Grabber #
**Version:** 0.1.0   
**Contributors:** [George Mamadashvili](https://profiles.wordpress.org/Mamaduka/), [Jay Wood](https://profiles.wordpress.org/phyrax/)    
**Description:** Class to grab images from the body of a website.   
**Author:** [WebDevStudios](http://webdevstudios.com)   
**Author URI:** http://webdevstudios.com/   
**Requires at least:** 3.6.0   
**Tested up to:**      4.2.2   
**Stable tag:**        0.1.0   
**License:**           GPLv2   
**License URI:**       http://www.gnu.org/licenses/gpl-2.0.html   

## Description ##

A PHP class to get a list of image URLs from a remote address and return them in an array.  Works in conjunction with
[CMB2 Remote Image Select Field](https://github.com/WebDevStudios/CMB2-Remote-Image-Select-Field) to provide users a facebook-style image selector for post-meta data.

The script looks for `og:image` tags first, then looks for all `<img>` tags within the content of the entire site.  Additionally it now provides a few extra checks to ensure
that the image should in-fact be pulled into the list, the rules are as follows:

1. If the image has no height/width element, it will not be pulled
1. If height or width are less than 70px, it will not be pulled
1. If image is relative such as `src="/relative/path.jpg"` it will not be pulled

This can be changed, or expanded upon by editing the `WDS_Image_Grabber::img_tags()` method.

## Usage Example ##
```php
$url = 'http://www.amazon.com//Sales-Grocery/b?ie=UTF8&node=52129011&ref_=amb_link_353229922_2';   
$grabber = new WDS_Image_Grabber( $url );   
$images = $grabber->get_images();   
var_dump( $images );   
```

## Installation ##

### Manual Installation ###

1. Upload the entire `/wds-image-grabber` directory to the `/wp-content/plugins/` directory.
2. Activate CMB2 Remote Image Select through the 'Plugins' menu in WordPress.

## Frequently Asked Questions ##

* None as of yet

## Changelog ##

### 0.1.0 ###
* First release

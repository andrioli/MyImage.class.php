# Myimage.class.php

A PHP class to resize, crop, generate thumbs and images with water mark.

## Examples

### Watermark:

To generate a image with water mark:

```php
<?php

// Load image 
$image = new MyImage("image.JPG");
// Load water mark
$wm = new MyImage("water_mark.JPG");
// Ensure that water mark fits on image size
if ($wm->width > $image->width || $wm->height > $image->height) {
    $wv->scale_to_fit($image->width, $image->height);
}
// Merge in center with transparency 60%
$image->merge($wm, 'CENTER', 60);
// Save
$image->save($directory = "/home/images/",
	              $name = "image+wm",
	              $type = "JPG",
	         $overwrite = true,
	           $quality = 80);
	           
?>
```

### Thumbnail:

To generate thumbnails use function thumb:

```php
<?php
           
$image = new MyImage("1.JPG");	           
$image->thumb(100, 75);
$image->save($directory = "/home/images/thumbs",
	              $name = "thumb",
	              $type = "JPG",
	         $overwrite = true,
	           $quality = 80);
	           
?>
```

## License

Do What The F*** You Want To Public License License.


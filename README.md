<div align="center">

## Resize Image in PHP \(JPG/JPEG\)


</div>

### Description

Resize an Image from any source. Could be local or remote. You can specify the image quality, height, width, etc. I believe this may only work with JPG/JPEG, I have only tried it with that. If it works with others, than cool! Vote! :)
 
### More Info
 
Shows before image, and After image, based on code specifications.

May not work with other formats than JPG/JPEG.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Nathan A\. Huebner](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/nathan-a-huebner.md)
**Level**          |Advanced
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |PHP 4\.0
**Category**       |[Internet/ Browsers/ HTML](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/internet-browsers-html__8-9.md)
**World**          |[PHP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/php.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/nathan-a-huebner-resize-image-in-php-jpg-jpeg__8-1831/archive/master.zip)

### API Declarations

Free code man!


### Source Code

```
<?
# If you think this script is too complicated, you should see other peoples scripts.
# I saw a script with 40 documents, and over 30,000 lines of code, just to do this.
$myimage="http://i2.microsoft.com/h/all/i/ms_masthead_8x6a_ltr.jpg";
$whereto = "C:\images\micrologo.jpg"; # Make sure this folder exists...
$mywidth=280; # sets the width of the NEW image
$myheight=35; # sets the height of the NEW image
$myquality=100; # sets the Quality of the NEW image (recommend 100 for best image)
echo "Original: $myimage (PSCode made me remove the SRC Code to show you the image, you will have to browse manually to find the image)<br><br>";
ResizeImage($myimage,$whereto,$mywidth,$myheight,$myquality);
echo "New Image: $whereto PSCode made me remove the SRC Code to show you the image, you will have to browse manually to find the image <br><br> <b>(If you see the image, then it saved correctly!)</b><br><br>Don't forget to vote! I had to look everywhere to learn this script.";
function ResizeImage($path_in,$path_out,$new_width,$new_height,$quality) {
# Set Quality to 100, or your images will look blurry.
# Reduce Quality if size is an issue.
# This will create an entirely NEW image, and will not remove the original
# IMPORTANT: I don't know if this works with anything but JPG/JPEG.
# You may need to convert your images to JPG/JPEG before using this.
		$width = $new_width;
		$height = $new_height;
  $new = ImageCreateTrueColor($width, $height);
  $source = ImageCreateFromJPEG($path_in);
  ImageCopyResampled($new, $source, 0, 0, 0, 0, $width, $height,
	ImageSX($source), ImageSY($source));
  ImageJPEG($new, $path_out, $quality);
# Returns the path of the resized image.
return $path_out;
}
?>
```


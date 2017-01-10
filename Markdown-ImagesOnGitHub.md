# Images on GitHub

To add an image to a Markdown document on GitHub use the syntax:

`![Image Tag](image_location.jpg)`


## Image Rotation

GitHub does not look at an image's exif data to correctly rotate images in Markdown documents.  An image will need to be edited and saved with the desired orientation in order for GitHub to display it correctly.

**Note:** On Linux, images can be batched converted using `exiftran` which will rotate files based on their exif data.

```
sudo apt-get install exiftran
exiftran -ai *.jpg
```

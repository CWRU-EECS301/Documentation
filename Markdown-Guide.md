# Markdown Guide

[Markdown](https://en.wikipedia.org/wiki/Markdown) is an easy to use markup language based on simple plain text formatting which can be rendered into HTML for viewing or PDF for distribution.

## GitHub Markdown
GitHub's web interface renders Markdown documents natively making it the first choice for documentation when using GitHub.  There's even a built-in editor for creating and editing Markdown documents right on the web interface.

To begin learning the Markdown syntax, here are some useful resources:

* [GitHub Quick Reference](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
* [GitHub Markdown Guide](https://guides.github.com/features/mastering-markdown/)
* [Interactive Markdown Tutorial](http://www.markdowntutorial.com)

:information_source: When browsing through GitHub repositories, any file with the **.md** extension is a Markdown file.

## Markdown Editors
There are a number of Markdown editors available for Window, macOS, and Linux.  Although, some editors may use their own variations of the Markdown syntax not supported by GitHub so the rendering could be different.

###Windows

* [MarkdownPad](http://markdownpad.com)
* [Notepad++](https://notepad-plus-plus.org/) / [Markdown PreviewHTML Plugin](Markdown-WindowsNotepadPlusPlusPlugin.md)

###Linux

* [Remarkable](https://remarkableapp.github.io/linux.html)
* [Emacs (with markdown-mode package)](http://jblevins.org/projects/markdown-mode/)

###macOS

* [MacDown](http://macdown.uranusjr.com)
* [Marked 2](http://marked2app.com/)/[Vim](http://www.vim.org/)

## Markdown Deployment
Markdown can be converted to either HTML or PDF for easier deployment.

Here's a list of conversion options:

* gitprint.com can convert text only Markdown documents from public GitHub repositories
* MacDown has an export function for both HTML and PDF
* Render with [grip](https://github.com/joeyespo/grip) and export using a web browser
* Command-line conversion with [markdown-pdf](https://github.com/alanshaw/markdown-pdf) (enables automatic conversion via scripts)

## Markdown Images 

Images are an important component of any document and Markdown makes adding images easy, simply using the following syntax:

`![Image Tag](image_file.jpg)`

Note, this assumes the image file is in the same directory as the Markdown document.  

Image paths can be relative (within the same repository):

`![Relative Path Image](../images/image_file.jpg)`

Or absolute (anywhere with a URL):

`![Absolute Path Image](https://case.edu/umc/media/caseedu/umc/images/logos/formalLogo560x285.jpg)`

### GitHub Image Rotation Problems

GitHub does not look at an image's exif data to correctly rotate images in Markdown documents.  An image will need to be edited and saved with the desired orientation in order for GitHub to display it correctly.

**Note:** On Linux, images can be batched converted using `exiftran` which will rotate files based on their exif data.

```
sudo apt-get install exiftran
exiftran -ai *.jpg
```

### Capturing Screen Snapshots

Screen snapshots can be an important part of documentation.  Here's a quick how-to for the major operating systems: [Screen Capture How-To](ScreenCapture-HowTo.md)

## Reference Material

* [Emoji Cheat Sheet](http://www.webpagefx.com/tools/emoji-cheat-sheet/)

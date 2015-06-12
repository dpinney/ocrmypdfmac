### Making PDFs Searchable

[Tesseract](https://code.google.com/p/tesseract-ocr/) is a great open source library for doing optical character recognition (OCR). But it's a little tricky to use it to make a PDF of images searchable, probably the biggest use case for OCR. Here's how to do that on a Mac.

(I tested all this and it worked as of 9 June 2015 on Mac OS X Yosemite 10.10.3. Your mileage may vary.)

### Steps for the Command Line

1. Install [Homebrew](http://brew.sh) or update your copy to the latest version (`brew update`).
2. Get ghostscript:
```brew install gs```
3. Make sure you get the latest version of tesseract:
```brew install --devel tesseract```
4. Now, let's say you scanned a magazine to input.pdf. Make a tiff first:
```gs -sDEVICE=tiff32nc -r300 -o mag.tif input.pdf```
5. Then OCR them:
```tesseract mag.tif output pdf```

Then open the resulting output.pdf in Preview.app and start searching for some words. They should highlight in the same location they were in the images. Tada!

### Shell Script Application

Or, just use .app in this repo by [downloading here](https://github.com/dpinney/ocrmypdf/archive/master.zip). The source .sh is also attached. I used Platypus to turn the shell script in to an app.

### Thanks

I was inspired by [ryanfb's instructions](https://ryanfb.github.io/etc/2014/11/13/command_line_ocr_on_mac_os_x.html) and this [discussion on stackflow](http://stackoverflow.com/questions/221455/ghostscript-pdf-tiff-conversion-is-awful-for-me-people-rave-about-it-i-alon) for how to get ghostscript to give pretty output.

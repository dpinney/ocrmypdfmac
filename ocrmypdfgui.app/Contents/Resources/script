#!/bin/sh
# By David Pinney on 12 June 2015.
# Description: run OCR on some PDFs.

export PATH=$PATH:/usr/local/bin

if [ $# == 0 ] ; then
    echo "Usage: OcrMyPdf.sh input1.pdf input2.pdf ... \nFor full usage details see https://gist.github.com/dpinney/46f0d93b220656ae6d43"
    exit 1;
fi

for path in "$@"
do
	gs -sDEVICE=tiff32nc -r300 -o "$path"-temp.tif "$path"
	tesseract "$path"-temp.tif "$path"-OCRd pdf
	rm "$path"-temp.tif
done
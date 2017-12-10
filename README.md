# markdown-dnd-images.el #

## Overview ##

Drag and drop files from your systems file manager onto your
current buffer and markdown-dnd-images will insert a markdown image
tag for you as well as make a copy of whatever file and put it in a
folder named like so

    ~/.emacs.d/markdown_image_files/images_for_Users_moorer_Documents_test.md/

where the markdown file you are inserting into is named
`/Users/moorer/Documents/test.md`

A new folder will be created for each markdown file you insert
into.

To change the image save location, please see the settings below.

You can drag and drop images from a web browser as well and the
program will try and download the image and put it in the local
folder.

Please note that on Linux images cannot be dragged from the Chrome browser.

Technically, it doesn't have to be inserted into a buffer currently
in markdown-mode, but it is going to insert the markdown image tag
regardless.

## Installation ##

To load...

Place this file `markdown-dnd-images.el` somewhere in your load
path and put this (or something similiar) in your .emacs file.

    (require 'markdown-dnd-images)
    
    ## Settings ##

    To save images in a directory other than ~/.emacs.d/markdown-image-files... The save directory may be relative to the buffer file (ex. images) or absolute (ex. ~/image_directory_all_files).

        (setq dnd-save-directory "images")

    By default, images are saved inside subfolder of the image directory that's unique to the buffer. The subfolder's named "images_for_buffername.file_ext". To save images without the subfolder:

        (setq dnd-save-buffer-name nil)
        
    Viewing saved images inline requires markdown-mode. To view images inline as they are dragged to the file:

        (setq dnd-view-inline t)
        
    To save the image's original url and access date:
        
        (setq dnd-capture-source t)

## Notes ##

Spaces in file names will be replaced with underscores.

## TODO ##

Currently, this will supercede the normal drag and drop behavior in
all buffers. TODO: only for certain buffers?

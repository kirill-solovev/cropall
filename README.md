# cropall

A small cross-platform python script to make cropping and resizing images fast.
Programs like gimp take way too long to start, open an image, crop it, export it.
A batch job/script can automate it but everything gets cropped at the same positions.
This sits in the middle, automating loading/clicking crop/save/next so your amazing
human vision can be used to quickly select what needs to be cropped and not wasted
on navigating clunky GUI hierarchies.
I'm surprised there aren't others out there, or maybe I didn't spend long enough
searching. `click2crop` looks good but is not free.

This is really a minimal GUI and preview for the following imagemagick command:

    convert in.jpg -crop <region> -resize <fit> out.jpg

## Forks

- [@rystraum](https://github.com/rystraum/cropall) has added a number of features such as rotation and keyboard shortcuts. See [#2](https://github.com/pknowles/cropall/issues/2).

# Install

    git clone https://github.com/pknowles/cropall.git

This needs...

-  python 3 (added to PATH)
   - python-tk
   - python-imaging-tk
   - pathlib
-  ImageMagick (added to PATH)

```
#Ubuntu
sudo apt-get install python python-tk python-imaging-tk imagemagick

#Fedora
sudo yum install python tkinter python-imaging-tk ImageMagick
```

I've installed and am using Pillow (`python-pillow` and `python-pillow-tk`) for this, but it may work with PIL.

> [Warning: Pillow and PIL cannot co-exist in the same environment. Before installing Pillow, please uninstall PIL.](http://pillow.readthedocs.org/en/latest/installation.html)
	
# Instructions

1. Run the script (double click if the OS knows to open-with or `./cropall.py`).

2. If there are images in the current working directory, it should start. Otherwise it will ask for a directory.

3. Click to select the region, scroll to adjust the size, click `crop` to start imagemagick and load the next image.

There are a few options at the top of the script file itself (I haven't bothered to provide GUI controls for some yet).


## Additional

Do whatever you want with it, within GPL3. The usual don't-blame-me-if-it-deletes-your-stuff.


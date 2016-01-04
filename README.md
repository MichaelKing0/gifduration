# gifduration.py

This script takes one or more animated GIF files as input and calculates their
total durations, returning zero for non-animated GIF files.


## Requirements

* [Pillow](https://github.com/python-imaging/Pillow)

Just run `pip install -r requirements.txt`, preferably outside a virtual environment if you want this script available system-wide.

## Installation

Clone the repository to some appropriate folder and symlink `gifduration.py` into your PATH, for example:

    ln -s ~/Code/gifduration/gifduration.py /usr/local/bin/gifduration

You may also have to make it executable:

    chmod +x /usr/local/bin/gifduration


## Usage

To get the duration of an animated GIF file, supply it as an argument:

    gifduration atom-heart-mother.gif

This will return the animation time (ms) in ms:

    atom-heart-mother.gif:
    2000

To also get the duration of each frame, use the `--verbose` (or `-v`) flag:

    gifduration --verbose atom-heart-mother.gif

This will return the frame animation time (ms), with the total duration like:

    atom-heart-mother.gif:
    30
    80
    30
    […]
    2000

You can get the durations of several animated GIF files at once just by supplying all of them as arguments, for example:

    gifduration atom-heart-mother.gif meddle.gif a-saucerful-of-secrets.gif

This will return something like:

    2000
    100
    0

GIF files that are not animated will return a duration of zero. All other file types will return the message `Not a GIF image`.


## Website

Go [here](http://gifduration.konstochvanligasaker.se/) for a simple web service carrying out pretty much the same thing.

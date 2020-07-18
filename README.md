
<!-- TOC GitLab -->

- [HOW-TO](#how-to)
- [Development](#development)
    - [Import](#import)
        - [Performance](#performance)
    - [Export](#export)
        - [Performance](#performance-1)
    - [Daemon](#daemon)
    - [Viewing](#viewing)

<!-- /TOC -->

Photon is the elementary particle of light and electromagnetic radiation. Photon is a mimimalistic no-cloud alternative to Google Cloud that provides phone-computer sync and smart archiving with open source tools.

Right now it moves images from folder A to B. It does nice things like renaming images in a neatly organized **YY-MM/timestamp.jpg** pattern, mime file type parsing, reading date from exif metadata when that's available, resolve collisions, move non-images to root.

# HOW-TO
Install dependencies: ripgrep, exiv2, ImageMagick

Run `setup.sh` to install to `.local/bin/`

Configure source and destination dirs in `move_pics` and run it.

# Development
## Import
TODO: Import video files to a videos dir.

TODO: Move dedup code to import script.

TODO: Dedup pictures. +done

### Performance
Parsing performance is good but could be better. In a modern desktop I moved 2GB of photos in less than a minute while also parsing over 1K of non-image files amounting over 1,5GB. Daily processing for non-photographers will be insignificant.

TODO: Parallelize IO writes to mitigate bottlenecks. +later

TODO: Multi-thread script execution. +later

## Export
TODO: Strip metadata and resize pictures. +done

TODO: Reencode videos.

### Performance
Image conversion is process intensive and unavoidably slow.

TODO: Detect and avoid already converted. +asap

TODO: Delete from mirror when their original were deleted. +asap

## Daemon
TODO: Daemon for importing/exporting when files change.

## Viewing
Is there anything great for this? Shotwell is the best Gnome tool that I know. I have my AutoWebGallery project but it's crude. I really just need a web gallery with a minimap scroller and tags searching and that throws anything at me like cat does. Network IO is not a constraint because it's local.

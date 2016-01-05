![SoundScrape!](http://i.imgur.com/nHAt2ow.png)

SoundScrape [![Build Status](https://travis-ci.org/Miserlou/SoundScrape.svg)](https://travis-ci.org/Miserlou/SoundScrape) [![PyPI](https://img.shields.io/pypi/dm/SoundScrape.svg?style=flat)](https://pypi.python.org/pypi/soundscrape/) [![Python 2](https://img.shields.io/badge/Python-2-brightgreen.svg)](https://pypi.python.org/pypi/soundscrape/) [![Python 3](https://img.shields.io/badge/Python-3-brightgreen.svg)](https://pypi.python.org/pypi/soundscrape/)
==============

**SoundScrape** makes it super easy to download artists from SoundCloud (and Bandcamp and MixCloud and AudioMack) - even those which don't have download links! It automatically creates ID3 tags as well (including album art), which is handy.

Is it easy to use?
---------
Install. Call it with the name of a _SoundCloud_ artist. Done.
```bash
pip install soundscrape
soundscrape rabbit-i-am
```

General Usage (all supported websites)
---------
Files are stored in the current folder:  
" _Artist Name - Track Title.mpX_ " <sub>(mp3 or mp4)</sub>

Using the _**-f**_ argument will automatically download files into folders:  
" _Artist Name - Album Name / 02 - Second Song.mpX_ "

You can use the _**-n**_ argument to only download a certain number of songs:
```bash
soundscrape rabbit-i-am -n 3
```
SoundScrape skips already downloaded songs, unless you use the _**-r**_ argument.

Using a full URL usually works as well, identifying which website you're trying to download from:
```bash
soundscrape https://mississippibones.bandcamp.com/
```
As a convenience method, SoundScrape can automatically _'open'_ downloaded files, using your system's _'open'_ command for file associations:
```bash
soundscrape lorn -of
```

SoundCloud
---------

Download a specific track (with _**-t**_ or the track URL):
```bash
soundscrape foolsgoldrecs -t danny-brown-dip
soundscrape https://soundcloud.com/foolsgoldrecs/danny-brown-dip
```
Download an entire set (with the set URL):
```bash
soundscrape https://soundcloud.com/vsauce-awesome/sets/awesome
```
Download all of an artist's liked items (with _**-l**_ or the likes URL):
```bash
soundscrape troyboi -l
soundscrape https://soundcloud.com/troyboi/likes
```
Download tracks from groups (with _**-g**_):
```bash
soundscrape chopped-and-screwed -gn 2
```
By default, SoundScrape will try to rip everything it can. However, if you only want to download tracks that have an official download available (which are typically at a higher-quality 320kbps bitrate), you can use the _**-d**_ argument:
```bash
soundscrape sly-dogg -d
```

Bandcamp
--------

Use the _**-b**_ argument along with an artist's username to parse the _"/music"_ page. SoundScrape will attempt to download each album and even orphan tracks.

**Note**: Currently, when using the _**-n**_ argument, the limit is evaluated for each album separately (meaning ```soundscrape -b whalerider -n 4``` will download 4 songs from each album).

Mixcloud
--------
SoundScrape can also grab mixes from Mixcloud. This feature is extremely experimental and is in no way guaranteed to work!

It finds the original mp3 of a mix and grabs that (with tags and album art) if it can, or else just gets the raw m4a stream.

Mixcloud currently only takes an invidiual mix. Capacity for a whole artist's profile due shortly.
```bash
soundscrape https://www.mixcloud.com/corenewsuploads/flume-essential-mix-2015-10-03/ -of
```

Audiomack
--------
Just for fun, SoundScrape can also download individual songs from Audiomack (with the _**-a**_ argument). Not that you'd ever want to.
```bash
soundscrape -a http://www.audiomack.com/song/bottomfeedermusic/top-shottas
```

Issues
-------
There's probably a lot more that can be done to improve this. Please file issues if you find them!

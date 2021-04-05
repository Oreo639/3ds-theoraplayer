# 3ds-Theora example
POC example of theora decoding for the Nintendo 3DS family of systems using libctru and citro2d.

## Usage
You can create a compatible video file using the following command:

`ffmpeg -i 'input.ext' -vcodec theora -vf scale=400:-1 -acodec libvorbis -ar 32000 "output.ogv"`

You can specify the video quality using the `-q:v` flag or the `-b:v` flag. If you are trying to play an animated show/movie try `-b:v` where as if you are trying to play a camera recording or live action show/movie try `-q:v`.

The `-q:v` flag dynamically changes the bitrate to maximize compression for slight sacrifice in quality.
The value can be any interger from 0-10 with 10 being the highest quality.
The 3ds has limited processing power and a slow filesystem speed so I do not recomment using 10, but any value between 0 and 7 should be fine. (4 is recommended)

The `-b:v` flag specifies a static bitrate to maximize quality over compression. Somewhere around 500k is recomended.

You can place your generated videos in the `/videos` directory on your sd card, if it doesn't exist, create it.

## Building
### Prerequsites:

[dkp-pacman](https://devkitpro.org/wiki/Getting_Started)

3ds-dev 3ds-libvorbisidec 3ds-libtheora

### Compiling:

Once you complete Prerequsites, run `make`.

## Copyright
This software is provided 'as-is', without any express or implied
warranty. In no event will the authors be held liable for any damages
arising from the use of this software.

Permission is granted to anyone to use this software for any purpose,
including commercial applications, and to alter it and redistribute it
freely, subject to the following restrictions:

   1. The origin of this software must not be misrepresented; you must not
   claim that you wrote the original software. If you use this software
   in a product, an acknowledgment in the product documentation would be
   appreciated but is not required.

   2. Altered source versions must be plainly marked as such, and must not be
   misrepresented as being the original software.

   3. This notice may not be removed or altered from any source
   distribution.


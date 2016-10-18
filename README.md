# FFmpeg - H3 / A83T platform (Cedrus HW Encoder - CMOS Camera)

FFmpeg with built in Cedrus264 HW Encoder for the H3 / A83T platform.
This was build on Ubuntu Xenial 16.04


Dependencies
============

	sudo apt-get install libmp3lame-dev libx264-dev libpulse-dev libv4l-dev


Source Code and Instructions
============================

https://github.com/linux-sunxi/libcedrus

https://github.com/uboborov/ffmpeg_h264_H3


How to use it
=============

- Attach you CMOS camera
- Clone the repo: git clone https://github.com/avafinger/ffmpeg_cedrus264_H3_A83T.git
- cd ffmpeg_cedrus264_H3_A83T
- Install the deb package: sudo dpkg -i ffmpeg-3.1.4_1.0-1.deb
- type: 

	sudo ffmpeg-3.1.4 -f v4l2 -channel 0 -video_size 1920x1080 -i /dev/video0 -pix_fmt nv12 -r 22 -c:v cedrus264 night_video_test4_1920x1080.mp4

- adjust the -r parameter and -qp for quality, in this test i got 22 FPS / 8475 kb/s

Play the MP4 file with your preferred application

Sample output is provided, a bit shaking, night.

There is no problem installing this version over an oficial version, they can co-exist.

Limitations
===========
 * Read the author's note - POC

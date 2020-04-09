# GstPerf

> A GStreamer element to measure framerate, bitrate and CPU usage

## Build Instructions

On Debian-based systems for x86 processors:
```bash
./autogen
./configure --prefix /usr/ --libdir /usr/lib/x86_64-linux-gnu/
make
sudo make install
```

For Arm processors (such as Nvidia Nano, Xavier, TX1/2...):

```bash
./autogen
./configure --libdir /usr/lib/aarch64-linux-gnu/
make
sudo make install
```

Configure options may vary according to your specific system.

## Usage

Just link in the `perf` element wherever you want to take the
measurements from. For example, record an MP4 file and print
framerate, bitrate and CPU usage measurements at the output of the
encoder:

```bash
gst-launch-1.0 -e videotestsrc ! x264enc ! perf ! qtmux print-arm-load=true ! filesink location=test.mp4
```

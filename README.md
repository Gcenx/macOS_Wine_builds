# Winehq macOS Builds

![Downloads count](https://img.shields.io/github/downloads/gcenx/macOS_Wine_builds/total.svg)

<br>

> [!NOTE]
> These will function like macOS pkg releases but are packaged within a `.tar.xz`.\
> I won't be providing a pkg installer, these packages prove `wine` that works for 32 & 64-bit windows binaires.

<br>

### How to install `wine-stable` using [brew](https://brew.sh/)
```
brew install --cask --no-quarantine wine-stable
```
This will install `Wine Stable` into `/Applications`

### Available packages
- `wine-stable`
- `wine@devel`
- `wine@staging`

<br>

#### How manually to install
Download the desired package from [releases](https://github.com/Gcenx/macOS_Wine_builds/releases) unpack, now move the `Wine *` bundle to `/Applications` and use as you would a Winehq release.

<br>

## Dependencies come from
- [MacPorts](https://www.macports.org/)
- [macports-wine](https://github.com/Gcenx/macports-wine) my MacPorts overlay

### Build dependencies 
- bison
- gstreamer-development
- mingw-w64
- pkgconfig
- Xcode

### Runtime dependencies
- freetype
- gstreamer-runtime
- gnutls-devel
- libinotify
- libsdl2
- moltenvk

<br>

## Configure Options
```
--build=x86_64-apple-darwin \
--enable-archs=i386,x86_64 \
--disable-tests \
--disable-winebth_sys \
--without-alsa \
--without-capi \
--with-coreaudio \
--with-cups \
--without-dbus \
--with-ffmpeg \
--with-freetype \
--with-gettext \
--without-gettextpo \
--without-gphoto \
--with-gnutls \
--without-gssapi \
--with-gstreamer \
--with-inotify \
--without-krb5 \
--with-mingw \
--without-netapi \
--with-opencl \
--without-opengl \
--without-oss \
--with-pcap \
--with-pcsclite \
--with-pthread \
--without-pulse \
--without-sane \
--with-sdl \
--without-udev \
--with-unwind \
--without-usb \
--without-v4l2 \
--with-vulkan \
--without-wayland \
--without-x
```

<br>

> [!CAUTION]
> My Antivirus says it's a VIRUS!!!\
> You need to contact your Antivirus/Anti-malware vendor to report these as false positives.\
> This started once wine moved to using *Mingw-gcc* to compile PE binaries.
> 
> __See the following examples:__
> - [CrossOver 19 and antivirus programs](https://www.codeweavers.com/support/forums/general/?t=27;msg=222870)
> - [Windows Defender detects Occamy.c trojan in steam proton 5.0 folder](https://github.com/ValveSoftware/Proton/issues/3593)

<br>

## gecko & mono are included
`wine-gecko` & `wine-mono` are included within these custom `Wine-*` packages, usually wine(64) will download and install .msi packages into each and every wineprefix increasing prefix size instead the "shared" versions are used to reduce prefix size.

<br>

> [!NOTE]
> ## Don't open wine issues here!;
> Wine bugs/regressions need to be reported via [Winehq Bugzilla](https://bugs.winehq.org/)\
> _Packaging related issues should be reported here._

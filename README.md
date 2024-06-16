# Winehq macOS Builds

![Downloads count](https://img.shields.io/github/downloads/gcenx/macOS_Wine_builds/total.svg)

<br>

#### _Please Note;_
These will function like macOS pkg releases but are packaged within a `.tar.xz`.\
I won't be providing a pkg installer, these packages prove `wine` and `wine64`

<br>

#### Minimum requirement of macOS High Sierra
If you need the latest versions of wine on legacy versions of macOS use [macports-wine](https://github.com/Gcenx/macports-wine)

<br>

### How to install using brew;

##### Available packages;
- `wine-stable`
- `wine@devel`
- `wine@staging`

<br>

##### Select the desired wine package to be installed, for an example I'll select `wine-stable`
```
brew install --cask --no-quarantine wine-stable
```
This will install `Wine Stable` into `/Applications`

<br>

#### How manually to install;
Download the desired package from [releases](https://github.com/Gcenx/macOS_Wine_builds/releases) unpack, now move the `Wine *` bundle to `/Applications` and use as you would a Winehq release.

<br>

## Build environment configuration;
- Xcode 15.4
- Mingw-w64 _v12_
- Mingw-gcc _v14.1.0_
- Mingw-binutils _v2.42_
- Build system includes fixes for [Bug 49199](https://bugs.winehq.org/show_bug.cgi?id=49199)

<br>

### Dependencies are built using;
- [macports-wine](https://github.com/Gcenx/macports-wine) overlay
- [macports](https://www.macports.org/)

<br>

## Configure Options used;
```
--disable-option-checking \
--disable-tests \
--enable-archs=i386,x86_64 \
--without-alsa \
--without-capi \
--with-coreaudio \
--with-cups \
--without-dbus \
--without-fontconfig \
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
--with-opengl \
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

## My Antivirus says it's a VIRUS!!!
You need to contact your Antivirus/Anti-malware vendor to report these as false positives.\
This started once wine moved to using *Mingw-gcc* to compile PE binaries.

__See the following examples:__
- [CrossOver 19 and antivirus programs](https://www.codeweavers.com/support/forums/general/?t=27;msg=222870)
- [Windows Defender detects Occamy.c trojan in steam proton 5.0 folder](https://github.com/ValveSoftware/Proton/issues/3593)

<br>

## gecko & mono are included;
`wine-gecko` & `wine-mono` are included within these custom `Wine-*` packages, usually wine(64) will download and install .msi packages into each and every wineprefix increasing prefix size instead the "shared" versions are used to reduce prefix size.

<br>

## Don't open wine issues here!;
Wine bugs/regressions need to be reported via [Winehq Bugzilla](https://bugs.winehq.org/)\
_Packaging related issues should be reported here._

# Winehq macOS Builds

![Downloads count](https://img.shields.io/github/downloads/gcenx/macOS_Wine_builds/total.svg)

<br>

#### _Please Note;_
These will function like macOS pkg releases but are packaged within a `.tar.xz`.\
I won't be providing a pkg installer, these packages include `wine` and `wine64`

<br>

#### Minimum requirement of macOS High Sierra
If you need the latest versions of wine on something legacy veraions of macOS use [macports-wine](https://github.com/Gcenx/macports-wine)

<br>

### How to install using brew;
First add `cask-versions`
```
brew tap homebrew/cask-versions
```

<br>

##### Available packages;
- `wine-stable`
- `wine-devel`
- `wine-staging`

<br>

##### Next select the desired wine package to be installed, for an example I'll select `wine-stable`
```
brew install --cask --no-quarantine wine-stable
```
This will install `Wine Stable` into `/Applications`

<br>

#### How manually to install;
Download the desired package from [releases](https://github.com/Gcenx/macOS_Wine_builds/releases) unpack, now move the `Wine *` bundle to `/Applications` and use as you would a Winehq release.

<br>

## Build environment configuration;
- cctools 973.0.1/ ld64 609
- MacOSX10.14u.sdk (macOS Mojave DevSDK for i386)
- MacOSX10.13.sdk (required by macports-port to compile for i386)
- Mingw-w64 _v11.0.1_
- Mingw-gcc _v13.1.0_
- Mingw-binutils _v2.40_
- Build system includes fixes for [Bug 49199](https://bugs.winehq.org/show_bug.cgi?id=49199)

<br>

### Dependencies are build using;
- [macports-wine](https://github.com/Gcenx/macports-wine) overlay
- [macports](https://www.macports.org/)

<br>

## Configure Options used;
```
--disable-option-checking \
--disable-tests \
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
--without-gstreamer \
--without-inotify \
--without-krb5 \
--with-mingw \
--without-netapi \
--with-opencl \
--with-opengl \
--without-oss \
--with-pcap \
--without-pcsclite \
--with-pthread \
--without-pulse \
--without-sane \
--with-sdl \
--without-udev \
--with-unwind \
--without-usb \
--without-v4l2 \
--without-wayland \
--without-x
```

<br>

## gecko & mono are included;
`wine-gecko` & `wine-mono` are included within these custom `Wine-*` packages, usually wine(64) will download and install .msi packages into each and every wineprefix increasing prefix size instead the "shared" versions are used to reduce prefix size.

<br>

## Don't open wine issues here!;
Wine bugs/regressions need to be reported via [Winehq Bugzilla](https://bugs.winehq.org/)\
_Packaging related issues should be reported here._

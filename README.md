# Winehq macOS Builds

Packages won't be pushed to Winehq until [bug 52354](https://bugs.winehq.org/show_bug.cgi?id=52354) is resolved.

![Downloads count](https://img.shields.io/github/downloads/gcenx/macOS_Wine_builds/total.svg)
 
#### _Please Note;_
These will function like macOS pkg releases but are packaged within a `.tar.xz`.\
I won't be providing a pkg installer, these packages include `wine` and `wine64`

#### Minimum requirement of macOS High Sierra
macOS High Sierra was released in 2017 and this is the last version of macOS to provide\
32Bit support within it's SDK the majority of wine development focuse is aimed at this.

If you need the latest versions of wine on something older you can use [macports-wine](https://github.com/Gcenx/macports-wine) my Macports overlay\
that allows compiling the last versions of wine from source on OS X 10.8 and later. This avoids complications with libraries as these will be built for your OS.

### How to install using brew;
First add `cask-versions`
```
brew tap homebrew/cask-versions
```

##### Available packages;
- `wine-stable`
- `wine-devel`
- `wine-staging`

##### Next select the desired wine package to be installed, for an example I'll select `wine-stable`
```
brew install --cask --no-quarantine wine-stable
```
This will install `Wine Stable` into `/Applications`

#### How manually to install;
Download the desired package from [releases](https://github.com/Gcenx/macOS_Wine_builds/releases) unpack, now move the `Wine *` bundle to `/Applications` and use as you would a Winehq release.

## Build environment configuration;
- cctools 973.0.1/ ld64 609/ LLVM 14.0.0
- MacOSX10.14.sdk (macOS Mojave sysroot i386)
- MacOSX10.13.sdk (required by macports-port to compile i386)
- Mingw-w64 _v10.0.0_
- Mingw-gcc _v12.2.0_
- Mingw-binutils _v2.39_
- Build system includes fixes for [Bug 49199](https://bugs.winehq.org/show_bug.cgi?id=49199)

### Dependencies are build using;
- [macports-gstreamer1](https://github.com/Gcenx/macports-gstreamer1) overlay
- [macports-wine](https://github.com/Gcenx/macports-wine) overlay
- [macports](https://www.macports.org/)

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
--with-gstreamer \
--without-inotify \
--without-krb5 \
--with-ldap \
--with-mingw \
--without-netapi \
--with-openal \
--with-opencl \
--with-opengl \
--without-oss \
--with-pcap \
--with-pthread \
--without-pulse \
--without-sane \
--with-sdl \
--without-udev \
--with-unwind \
--without-usb \
--without-v4l2 \
--without-x
```

## gecko & mono are included;
`wine-gecko` & `wine-mono` are included within these custom `Wine-*` packages, usually wine(64) will download and then install .msi packages into each and every wineprefix increasing prefix size instead the "shared" packages are used to reduce prefix size.

## Don't open wine issues here!;
Wine bugs/regressions need to be reported via [Winehq Bugzilla](https://bugs.winehq.org/)\
Packaging related issues should be reported here.

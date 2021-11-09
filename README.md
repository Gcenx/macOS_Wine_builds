# Winehq WIP macOS Builds

These builds won't be uploaded directly to Winehq until were happy with them, on our current timeline the plan is to have these pushed to Winehq around Wine-7.0.

![Downloads count](https://img.shields.io/github/downloads/gcenx/macOS_Wine_builds/total.svg)
 
#### _Please Note;_
These will function like macOS pkg releases but are packaged within a `.tar.xz`.\
I won't be providing a pkg installer, these packages include `wine` and `wine64`

#### Minimum requirement of macOS High Sierra
macOS High Sierra was released in 2017 and this is the last version of macOS to provide\
32Bit support within it's SDK the majority of wine development focuse is aimed at this.

If you need the latest versions of wine on something older you can use [macports-wine](https://github.com/Gcenx/macports-wine) my Macports overlay\
allows compiling the last versions of wine from source on OS X 10.8 and later. This avoids complications with libraries as these will be built for your OS.

### How to install using brew;
First add `cask-versons`
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
- XCode _v11.3.1_
- MacOSX10.14.sdk (Patched in 32Bit support)
- Mingw-w64 _v9.0.0_
- Mingw-gcc _v11.2.0_
- Mingw-binutils _v2.37_
- XQuartz _v2.8.1_ was used for X11
- Build system includes fixes for [Bug 49199](https://bugs.winehq.org/show_bug.cgi?id=49199)

### Dependencies are build using;
- [macports-gstreamer1](https://github.com/Gcenx/macports-gstreamer1) overlay
- [macports-wine](https://github.com/Gcenx/macports-wine) overlay
- Macports

## Configure Options used;
```
--disable-option-checking \
--disable-tests \
--without-alsa \
--without-capi \
--with-cms \
--with-coreaudio \
--with-cups \
--without-curses \
--without-dbus \
--with-faudio \
--without-fontconfig \
--with-freetype \
--with-gcrypt \
--with-gettext \
--without-gettextpo \
--without-gphoto \
--with-gnutls \
--without-gsm \
--without-gssapi \
--with-gstreamer \
--without-hal \
--without-inotify \
--with-jpeg \
--with-jxrlib \
--without-krb5 \
--with-ldap \
--with-mingw \
--with-mpg123 \
--without-netapi \
--with-openal \
--with-opencl \
--with-opengl  \
--without-oss \
--with-pcap \
--with-png \
--with-pthread \
--without-pulse \
--without-quicktime \
--without-sane \
--with-sdl \
--with-tiff \
--without-udev \
--with-unwind \
--with-usb \
--without-v4l2 \
--without-xattr \
--with-xml \
--with-xslt \
--with-osmesa \
--with-xcomposite \
--with-xcursor \
--with-xfixes \
--with-xinerama \
--with-xinput \
--with-xinput2 \
--with-xrandr \
--with-xrender \
--with-xshape \
--with-xshm \
--with-xxf86vm \
--with-x \
--x-include=/opt/X11/include \
--x-lib=/opt/X11/lib
```

## gecko & mono are included;
`wine-gecko` & `wine-mono` are included within these custom `Wine-*` packages, usually wine(64) will download and then install .msi packages into each and every wineprefix increasing prefix size instead the "shared" packages are used to reduce prefix size.

## Don't open wine issues here!;
Wine bugs/regressions need to be reported via [Winehq Bugzilla](https://bugs.winehq.org/)\
Packaging related issues should be opened here.\
As I’m not too familiar with brew so any issues with the provided casks/formulas should be reported.

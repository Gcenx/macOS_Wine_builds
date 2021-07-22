# Winehq style macOS Builds

Currently Winehq is not providing macOS builds until they replace the now deprecated builder, as a temporary measure I'll attach `wine-stable`, `wine-devel` & `wine-staging` builds here that includes most dependencies, meaning XQuartz-2.7.7 or later is not required unless you desire to use X11 over macDriver.

![Downloads count](https://img.shields.io/github/downloads/gcenx/macOS_Wine_builds/total.svg)
 
#### _Please Note;_
These will function like macOS pkg releases but are packaged within a `.tar.xz`.\
I won't be making pkg installer, these packages include `wine` and `wine64`

### How to install using brew;
First add my tap
```
brew tap gcenx/wine
```
##### The tap provides;
- `gcenx-wine-stable`
- `gcenx-wine-devel`
- `gcenx-wine-staging`

##### Next select the desired wine package to be installed, for an example I'll select `gcenx-wine-stable`
```
brew install --cask --no-quarantine gcenx-wine-stable
```
This will install `Wine Stable` into `/Applications` and function as the official brew cask would (but _doesn't_ require XQuartz)

#### How manually to install;
Download the desired package from [releases](https://github.com/Gcenx/macOS_Wine_builds/releases) unpack, now move the `Wine *` bundle to `/Applications` and use as you would a Winehq release.


## Build environment configuration;
- _CodeWeavers custom llvm/clang-8_ (wine32on64 sources only)
- XCode _v11.3.1_
- MacOSX10.14.sdk (Patched in 32Bit support)
- Mingw-w64 _v9.0.0_
- Mingw-gcc _v11.1.0_
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
`wine-gecko` & `wine-mono` are included within these custom `Wine-*` packages, usually wine(64/32on64) will download and then install .msi packages into each and every wineprefix increasing prefix size instead the "shared" packages are used to reduce prefix size.

## Don't open wine issues here!;
Wine bugs/regressions need to be reported via [Winehq Bugzilla](https://bugs.winehq.org/)\
Packaging related issues should be opened here.\
As I’m not too familiar with brew so any issues with the provided casks/formulas should be reported.

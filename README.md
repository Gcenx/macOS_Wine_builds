# Winehq style macOS Builds

Currently Winehq is not providing macOS builds until they replace the now deprecated builder, as a temporary measure I'll attach `wine-stable`, `wine-devel` & `wine-staging` builds here that includes most dependencies, meaning XQuartz-2.7.7 or later is not required unless you desire to use X11 over macDriver.

![Downloads count](https://img.shields.io/github/downloads/gcenx/macOS_Wine_builds/total.svg)
 
 ### Currently avalible on releases;
 - `wine-devel-5.21-osx64.tar.7z` (includes workaround for [Bugzilla 49940](https://bugs.winehq.org/show_bug.cgi?id=49940))
 - `wine-devel-5.20-osx64.tar.7z` (includes workaround for [Bugzilla 49940](https://bugs.winehq.org/show_bug.cgi?id=49940))
 - `wine-devel-5.19-osx64.tar.7z`
 - `wine-devel-5.18-osx64.tar.gz`
 - `wine-devel-5.17-osx64.tar.gz` (includes patchs for [Bugzilla 49624](https://bugs.winehq.org/show_bug.cgi?id=49624))
 - `wine-devel-5.16-osx64.tar.gz`
 - `wine-devel-5.15-osx64.tar.gz`
 - `wine-devel-5.14-osx64.tar.gz`
 - `wine-devel-5.13-osx64.tar.gz`
 - `wine-devel-5.12-osx64.tar.gz`
 - `wine-devel-5.11-osx64.tar.gz`
 - `wine-devel-5.9-osx64.tar.gz`
 - `wine-stable-5.0.3-osx64.tar.gz` (includes patch for [Bugzilla 49774](https://bugs.winehq.org/show_bug.cgi?id=49774) & workaround for [Bugzilla 49940](https://bugs.winehq.org/show_bug.cgi?id=49940))
 - `wine-stable-5.0.2-1-osx64.tar.gz` (includes patch for [Bugzilla 49774](https://bugs.winehq.org/show_bug.cgi?id=49774))
 - `wine-stable-5.0.2-osx64.tar.gz`
 - `wine-stable-5.0.1-osx64.tar.gz`
 - `wine-staging-5.21-osx64.tar.7z` (includes workaround for [Bugzilla 49940](https://bugs.winehq.org/show_bug.cgi?id=49940))
 - `wine-staging-5.20-osx64.tar.7z` (includes workaround for [Bugzilla 49940](https://bugs.winehq.org/show_bug.cgi?id=49940))
 - `wine-staging-5.19-osx64.tar.7z`
 - `wine-staging-5.18-osx64.tar.gz`
 - `wine-staging-5.17-osx64.tar.gz` (includes patchs for [Bugzilla 49624](https://bugs.winehq.org/show_bug.cgi?id=49624))
 - `wine-staging-5.16-osx64.tar.gz`
 - `wine-staging-5.15-osx64.tar.gz`
 - `wine-staging-5.14-osx64.tar.gz`
 - `wine-staging-5.13-osx64.tar.gz`
 - `wine-staging-5.12.1-osx64.tar.gz`
 - `wine-staging-5.11-osx64.tar.gz`
 - `wine-staging-5.9-osx64.tar.gz`
 
#### _Please Note;_
These will function like macOS pkg releases but are packaged within a `.tar.gz`.\
I won't be making pkg installer, these packages include `wine` and `wine64`

### How to install using brew;
First add my tap
```
brew tap gcenx/wine
```
##### The tap provides;
- `gcenx-wine-stable` (wine-stable-5.0.2-1)
- `gcenx-wine-devel` (wine-devel-5.21)
- `gcenx-wine-staging` (wine-staging-5.21)

##### Next select the desired wine package to be installed, for an example I'll select `gcenx-wine-stable`
```
brew cask install --no-quarantine gcenx-wine-stable
```
This will install `Wine Stable` into `/Applications` and function as the official brew cask would (but _doesn't_ require XQuartz)

#### How manually to install;
Download the desired package from [releases](https://github.com/Gcenx/macOS_Wine_builds/releases) unpack, now move the `Wine *` bundle to `/Applications` and use as you would a Winehq release.

## Build environment configuration;
- CodeWeavers custom llvm/clang-8 (Wine Crossover only)
- MacOSX10.13.sdk (with QuickTime.framework from MacOSX10.11.sdk)
- Mingw-w64-v8
- Mingw-gcc-10.2
- Mingw-w64-binutils-2.35.1
- Dependencies are build using macports with [macports-wine](https://github.com/Gcenx/macports-wine)
- XQuartz-2.7.7 was used for X11
- Build system includes fixes for [Bug 49199](https://bugs.winehq.org/show_bug.cgi?id=49199)

## Configure Options used;
```
--disable-option-checking \
--disable-tests \
--without-alsa \
--without-capi \
--with-cms \
--with-coreaudio \
--with-cups \
--with-curses \
--without-dbus \
--with-faudio \
--without-fontconfig \
--with-freetype \
--with-gcrypt \
--without-gettext \
--without-gettextpo \
--without-gphoto \
--with-glu \
--with-gnutls \
--without-gsm \
--without-gssapi \
--with-gstreamer \
--without-gtk3 \
--without-hal \
--without-inotify \
--with-jpeg \
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
--without-vkd3d \
--without-xattr \
--with-xml \
--with-xslt \
--without-va  \
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
`wine-gecko` & `wine-mono` are included within these custom `Wine-*` packages, usually wine(64) will download and then install .msi packages into each and every wineprefix increasing prefix size instead the "shared" packages were used to help reduce prefix size

## Don't open issues for wine issues!
Any wine bugs or regressions report those to [Winehq Bugzilla](https://bugs.winehq.org/), for package related issues related to missing dylib or a dylib refusing to load on OS X 10.9 then open an issue so it can be resolved.

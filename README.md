# Winehq style macOS Builds
 
Currently Winehq is not providing macOS builds until they replace the now deprecated builder,\
so as I temporary measure I'll attach `wine-staging` builds here that includes most\
dependencies meaning XQuartz-2.7.7 or later is not required unless you desire to use X11 over macDriver.
 
 Currently avalible on releases section;
 - `wine-staging-5.9-osx64.tar.gz`
 - `wine-devel-5.9-osx64.tar.gz`

_Please Note;_ these will function like macOS pkg releases but are packaged within a `.tar.gz`.\
I won't be making pkg installer, these packages include `wine` and `wine64`

## Build environment configuration;
- CodeWeavers custom llvm/clang-8
- MacOSX10.13.sdk (QuickTime.framework from MacOSX10.11.sdk)
- Mingw-w64-9.3.0
- Mingw-w64-binutils with [Proton patches](https://github.com/GloriousEggroll/proton-ge-custom/tree/proton-ge-5-MF/mingw-w64-patches)
- Dependencies are build using macports with [macports-wine](https://github.com/Gcenx/macports-wine)
- Build system includes a fix for [Bug 49199](https://bugs.winehq.org/show_bug.cgi?id=49199)

## Configure Options used;
```
--disable-option-checking \
--disable-tests --without-alsa \
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
--without-ldap \
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
--without-xshm \
--with-xslt \
--with-zlib \
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
--x-lib=/opt/X11/libb
```

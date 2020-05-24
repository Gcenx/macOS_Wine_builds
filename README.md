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
- Mingw-w64-binutils [Proton patches](https://github.com/GloriousEggroll/proton-ge-custom/tree/proton-ge-5-MF/mingw-w64-patches)
- Dependencies are build using macports with [macports-wine](https://github.com/Gcenx/macports-wine)
- Build system includes a fix for [Bug 49199](https://bugs.winehq.org/show_bug.cgi?id=49199)

# MPV Player Win64 Build

## Installation
Grab and extract the All-in-One archive from <https://github.com/HedioKojima/mpv-win64/releases>  
**Bleeding Edge** weekly build is based on the git trunk code of mpv, FFmpeg and libplacebo. It includes the newest features and bug fixes but may be less stable  
Only the **x86-64-v3** build is produced; it is optimized for CPUs that support the AVX2 instruction set, this includes most CPUs after 2013  
All libraries except the MSYS2 toolchain are compiled from their upstream git repositories  
You can also manually install these pacman-based packages if you are using MSYS2  
All my builds are portable

## Main project site:
<https://mpv.io/>

## Configuration
<https://mpv.io/manual/>  
All your configurations can be saved within the ***portable_config*** subdirectory

## Awesome Links
- [User Scripts from Official](https://github.com/mpv-player/mpv/wiki/User-Scripts)
- [Default MPV Setting](https://github.com/mpv-player/mpv/blob/master/etc/mpv.conf)
- [Default MPV Key Binding](https://github.com/mpv-player/mpv/blob/master/etc/input.conf)
### Lua Plugin
- [uosc](https://github.com/tomasklaen/uosc)
- [thumbfast](https://github.com/po5/thumbfast)
### Shader
- [Anime4K](https://bloc97.github.io/Anime4K/)
- [SSim/Krig](https://gist.github.com/igv)
- [FSRCNNX](https://github.com/igv/FSRCNN-TensorFlow/releases)
- [ACNet](https://github.com/TianZerL/ACNetGLSL/releases)

## How to Compile
Fork this repo and build these packages by Github Action  
Run the `toolchain` workflow first: it prepares the MSYS2/mingw-w64 cache and publishes the `mcfgthread` package to the `bleeding_edge-x86-64-v3` release  
Then run the `batch-bleeding_edge-weekly` workflow (it also runs weekly on schedule)  
**NOTICE**  
Don't build it on your personal msys2 environment unless it was in sandbox, these shitty scripts will spoil your whole weekend!

## Detail
The FFmpeg and MPV library were built with the following libraries
- ffnvcodec: Nvidia Hardware Accelerated video Encoding/Decoding
- lcms2: Reading ICC Profiles for Your Monitor
- libass/freetype2/fribidi/harfbuzz: Subtitle Support
- luajit: Lua Plugin
- shaderc/spirv-cross/vulkan: D3D11 & Vulkan Context
- libplacebo: cloned and built from upstream git inside the mpv job

## TODO ???
### Build FFmpeg with x264/x265/rav1e/SVT-AV1/VVenC for video encoding
I prefer to directly use these utilities
### Build FFmpeg with libfdk_aac for high quality AAC audio encoding
Yes, Fraunhofer AAC produce better aac than FFmpeg native, but it is still not in the top tier. I recommend you to use xHE-AAC or Apple AAC instead
### Build libass with fontconfig for POSIX-like system font configuration
Fontconfig sucks on windows, and... do you really want to learn it?
### Build FFmpeg with dav1d for av1 decoding
~~Today all public av1 videos are just demos. I suggest you to try vvc for the purpose of testing~~  
ffmpeg has built-in av1 & vvc decoder now

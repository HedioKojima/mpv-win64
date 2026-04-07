# MPV Player Win64 Build

## Installation
Grab and extract the All-in-One archive from <https://github.com/nyfair/mpv-win64/releases>  
**Bleeding Edge** weekly build is based on the git trunk code of mpv and libplacebo. It includes the newest features and bug fixes but may be less stable  
**x86-64-v3** build is optimized for CPUs that support the AVX2 instruction set, this includes most CPUs after 2013  
You can also manually install these pacman-based packages if you are using MSYS2  
All my builds are portable and compiled with VapourSynth support, these plugins will have no effect if MPV can't find python environment

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
### Shader
- (https://github.com/hooke007/mpv_PlayKit/tree/main/portable_config/shaders)
## How to Compile
Fork this repo and build these packages by Github Action  
**NOTICE**  
Don't build it on your personal msys2 environment unless it was in sandbox, these shitty scripts will spoil your whole weekend!

## Detail
The FFmpeg and MPV library were built with the following libraries
- nvcodec: Nvidia Hardware Accelerated video Encoding/Decoding
- lcms2: Reading ICC Profiles for Your Monitor
- libass/freetype2/fribidi/harfbuzz: Subtitle Support
- luajit: Lua Plugin
- shaderc/spirv/libplacebo: D3D11 & Vulkan Context
- libbluray: Parsing BD
- libwebp: WebP Image Encoding/Decoding
- libjxl/highway/brotli: JPEG XL Image Encoding/Decoding

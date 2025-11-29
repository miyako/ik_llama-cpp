![version](https://img.shields.io/badge/version-20%2B-E23089)
![platform](https://img.shields.io/static/v1?label=platform&message=mac-intel%20|%20mac-arm%20|%20win-64&color=blue)
[![license](https://img.shields.io/github/license/miyako/ik_llama-cpp)](LICENSE)
![downloads](https://img.shields.io/github/downloads/miyako/ik_llama-cpp/total)

# ik_llama-cpp
Local inference engine

### Apple Silicon

```
cmake -S . -B build_arm -DGGML_METAL=ON
cmake --build build_arm --config Release
```

### Intel

```
cmake -S . -B build_rosetta \
  -DLLAMA_NATIVE=OFF \
  -DCMAKE_C_FLAGS="-msse3 -mssse3 -msse4.1 -msse4.2 -mavx -mavx2 -mfma -mf16c" \
  -DCMAKE_CXX_FLAGS="-msse3 -mssse3 -msse4.1 -msse4.2 -mavx -mavx2 -mfma -mf16c"
cmake --build build_amd --config Release
```

### Windows

```
cmake -S . -B build -A X64 -DBUILD_SHARED_LIBS=OFF
cmake --build build --config Release
```

add 

```c
#define __AVX2__ 1
```

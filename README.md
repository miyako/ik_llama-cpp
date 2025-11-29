![version](https://img.shields.io/badge/version-20%2B-E23089)
![platform](https://img.shields.io/static/v1?label=platform&message=mac-intel%20|%20mac-arm%20|%20win-64&color=blue)
[![license](https://img.shields.io/github/license/miyako/ik_llama-cpp)](LICENSE)
![downloads](https://img.shields.io/github/downloads/miyako/ik_llama-cpp/total)

# ik_llama-cpp
Local inference engine

**aknowledgements**: [ikawrakow/ik_llama.cpp](https://github.com/ikawrakow/ik_llama.cpp)

### Apple Silicon

```
cmake -S . -B build_arm -DGGML_METAL=ON -DBUILD_SHARED_LIBS=OFF
cmake --build build_arm --config Release
```

### Intel

```
cmake -S . -B build_amd \
  -DLLAMA_NATIVE=OFF -DBUILD_SHARED_LIBS=OFF \
  -DCMAKE_C_FLAGS="-msse3 -mssse3 -msse4.1 -msse4.2 -mavx -mavx2 -mfma -mf16c" \
  -DCMAKE_CXX_FLAGS="-msse3 -mssse3 -msse4.1 -msse4.2 -mavx -mavx2 -mfma -mf16c"
cmake --build build_amd --config Release
```

### Windows

Not supported (original llama.cpp is used instead)

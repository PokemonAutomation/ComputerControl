# Build ONNX Runtime From Source

We use ONNX Runtime to run ML model inference efficiently. To download the source code:

```
git clone --recursive https://github.com/Microsoft/onnxruntime.git
cd onnxruntime
```

Make sure the downloaded onnxruntime/ is in the same folder as our project's codebase Arduino-Source/ (or Arduino-Source-Internal/ for internal repo).

## macOS

Build command:

```
./build.sh --config Release --build_shared_lib --parallel --compile_no_warning_as_error --skip_submodule_sync --cmake_extra_defines CMAKE_OSX_ARCHITECTURES=arm64 --cmake_extra_defines FETCHCONTENT_TRY_FIND_PACKAGE_MODE=NEVER --use_coreml
```

If you want some debug info, change "Release" to "RelWithDebInfo".

### Explain the build command

By default, the build script uses the third-party libraries installed in the OS system as dependency. but this may create conflict: the ONNX library installed by Homebrew may be too old for the latest ONNX Runtime. To avoid this, you need to add
`--cmake_extra_defines FETCHCONTENT_TRY_FIND_PACKAGE_MODE=NEVER` as above to let the build script download the correct third-party libraries from server.
Alternatively, you can use `--use_vcpkg` to achieve the same result.

`--use_coreml` is needed to build ONNX Runtime with CoreML, Apple's ML acceleration library.


If you encounter such error as below:
```
CMake Error at .../onnxruntime/build/MacOS/Release/_deps/fp16-src/CMakeLists.txt:1 (CMAKE_MINIMUM_REQUIRED):
  Compatibility with CMake < 3.5 has been removed from CMake.

  Update the VERSION argument <min> value.  Or, use the <min>...<max> syntax
  to tell CMake that the project requires at least <min> but has been updated
  to work with policies introduced by <max> or earlier.

  Or, add -DCMAKE_POLICY_VERSION_MINIMUM=3.5 to try configuring anyway.
```
this means your CMake is too old or too new to work with the downloaded third-party libraries. If too old, upgrade your CMake. If too new, you can just open the CMakeLists.txt file that has the error and comment out or delete the line that throws the error:
```
CMAKE_MINIMUM_REQUIRED(VERSION 2.8.12 FATAL_ERROR)
```

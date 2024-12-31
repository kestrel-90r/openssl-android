# OpenSSL for Android (x86_64)

Custom build of OpenSSL for Android x86_64 platform, specifically configured for use with libcurl in Android native applications.

## Build Configuration

- Target Platform: Android (x86_64)
- Android Version: Android 12 (API Level 31)
- Build Type: Static Libraries (libssl.a, libcrypto.a)
- Compiler: Clang 14
- NDK: r23b
- Build Output:
  - libssl.a
  - libcrypto.a
  - include/openssl/*

## Dependencies

- Android NDK r23b
- Clang 14

## Build Instructions

1. Set environment variables:

export ANDROID_NDK_HOME=/path/to/android-ndk
export HOST_TAG=linux-x86_64
export TOOLCHAIN=$ANDROID_NDK_HOME/toolchains/llvm/prebuilt/$HOST_TAG

export CC=$TOOLCHAIN/bin/x86_64-linux-android31-clang
export CXX=$TOOLCHAIN/bin/x86_64-linux-android31-clang++

2. Configure and build:

./Configure android-x86_64 \
-DANDROID_API_=31 \
no-shared \
no-tests \
CC=x86_64-linux-android31-clang
make -j$(nproc)

## Output Files

The build process generates:
- `libssl.a`: SSL/TLS protocol implementation
- `libcrypto.a`: Core cryptographic functions
- `include/openssl/*`: Header files

## Usage with libcurl

This build is specifically configured to work with libcurl for Android applications. 
See the companion [libcurl-android](https://github.com/YOUR_USERNAME/libcurl-android) repository.

## License

[OpenSSL License](https://www.openssl.org/source/license.html)

## Original Project

This is a fork of [openssl/openssl](https://github.com/openssl/openssl) customized for Android builds.


























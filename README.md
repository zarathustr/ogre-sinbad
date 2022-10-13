# Ogre-Sinbad
This repo contains the adjusted codes for successful build of Ogre3D 1.9 on Android platform. This repo has been tested with macOS 10.15, 12.6 and Ubuntu 18.04.

# Dependencies
The provided repo utilizes the compilation on 32-bit armeabi-v7a ABI. For dependencies, please refer to https://github.com/zarathustr/ogre-deps
Typically, the dependencies include FreeType, FreeImage, OIS, libzzip, etc.

# Compilation
We use an Android-24 base with Native Development Kit (NDK) version 23. We put the dependencies in the directory ```/Users/zarathustra/inmo/android-deps```. The complete command is as follows:

```
ANDROID_NDK=/Users/zarathustra/Library/Android/sdk/ndk/23.1.7779620 ANDROID_SDK_ROOT=/Users/zarathustra/Library/Android/sdk ANDROID_NATIVE_API_LEVEL=24 STRIP=/Users/zarathustra/Library/Android/sdk/ndk/23.1.7779620/toolchains/llvm/prebuilt/darwin-x86_64/bin/llvm-strip ANDROID_PLATFORM=android-24 ANDROID_ABI=armeabi-v7a cmake -DCMAKE_TOOLCHAIN_FILE=/Users/zarathustra/Library/Android/sdk/ndk/23.1.7779620/build/cmake/android.toolchain.cmake -DANDROID_ABI=armeabi-v7a -DCMAKE_BUILD_TYPE=Release -DANDROID_NATIVE_API_LEVEL=24 -DANDROID_STL=c++_static -DBUILD_SHARED_LIBS=OFF -DBUILD_ANDROID_PROJECTS=OFF   -DANDROID_PLATFORM=24 -DCMAKE_PREFIX_PATH=/Users/zarathustra/inmo/android-deps -DGFLAGS_INCLUDE_DIR=/Users/zarathustra/inmo/android-deps/include -DGFLAGS_LIBRARY=/Users/zarathustra/inmo/android-deps/lib/libgflags.a -DGLOG_INCLUDE_DIR=/Users/zarathustra/inmo/android-deps/include -DGLOG_LIBRARY=/Users/zarathustra/inmo/android-deps/lib/libglog.a -DEIGEN_INCLUDE_DIR=/usr/local/include/eigen3 -DEIGEN3_INCLUDE_DIR=/usr/local/include/eigen3 -DCERES_INCLUDE_DIR=/Users/zarathustra/inmo/android-deps/include -DCERES_LIBRARY=/Users/zarathustra/inmo/android-deps/lib/libceres.a -DOGRE_BUILD_PLATFORM_ANDROID=TRUE -DFREETYPE_FT2BUILD_INCLUDE_DIR=/Users/zarathustra/inmo/android-deps/include -DOIS_INCLUDE_DIR=/Users/zarathustra/inmo/android-deps/include/OIS -DOGRE_DEPENDENCIES_DIR=/Users/zarathustra/inmo/android-deps -DCMAKE_INSTALL_PREFIX=/Users/zarathustra/inmo/android-deps ..
```

Note that we have the environment variables set as:
```
export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0_202.jdk/Contents/Home
export JDK_ROOT=/Library/Java/JavaVirtualMachines/jdk1.8.0_202.jdk/Contents/Home/jre/bin
export ANDROID_SDK_ROOT=/Users/zarathustra/Library/Android/sdk
export ANDROID_NDK_PATH=/Users/zarathustra/Library/Android/sdk/ndk/23.1.7779620
export ANDROID_NDK_ROOT=/Users/zarathustra/Library/Android/sdk/ndk/23.1.7779620
export ANDROID_NDK_PLATFORM=android-27

export PATH=/Users/zarathustra/Library/Android/sdk/ndk/23.1.7779620:/Library//Java/JavaVirtualMachines/jdk1.8.0_202.jdk/Contents/Home/bin:/Users/zarathustra/Library/Android/sdk/tools:/Users/zarathustra/kalibr_ws/devel/lib:$PATH
```

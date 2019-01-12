# CLion With Bazel Bugs Demo

This repository is intended to be used to demonstrate two potential bugs in the
CLion Bazel plugin:

- CLion does not find stdlib `assert()` macro (Issue #493)
- CLion Fails to Debug `cc_binary` target (Issue #494)

I intend to file each as a GitHub issue at `bazelbuild/intellij`.


## dwtj's Testing Environment

- macOS 10.14.2 (Mojave)
- CLion v2018.2.7 (Though CLion v2018.3.0+ are more recent, they don't seem to
be compatible with the latest versions of the plugin.)
- Two versions of the plugin, `https://github.com/bazelbuild/intellij`:
    - v2018.12.03.0.2 (latest pre-built release, retrieved within CLion)
    - `0f45ef4` (built from source)
- File System: APFS (Case-sensitive, Encrypted)

```
$ xcodebuild -version
Xcode 10.1
Build version 10B61
$ c++ --version
Apple LLVM version 10.0.0 (clang-1000.11.45.5)
Target: x86_64-apple-darwin18.2.0
Thread model: posix
InstalledDir: /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin
$ bazel version
WARNING: --batch mode is deprecated. Please instead explicitly shut down your Bazel server using the command "bazel shutdown".
INFO: Invocation ID: d1b8eba4-dc65-4103-9351-c84a51b0c384
Build label: 0.21.0
Build target: bazel-out/darwin-opt/bin/src/main/java/com/google/devtools/build/lib/bazel/BazelServer_deploy.jar
Build time: Wed Dec 19 12:57:09 2018 (1545224229)
Build timestamp: 1545224229
Build timestamp as int: 1545224229
```

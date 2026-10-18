# liblsl-ci-build

Automated CI/CD pipelines for building [liblsl](https://github.com/sccn/liblsl) dynamic libraries across multiple platforms using GitHub Actions.

## Used by SharpLSL

During the packaging process of [SharpLSL](https://github.com/SharpLSL/SharpLSL), these liblsl binary archives are automatically downloaded and bundled into NuGet packages named `SharpLSL.Native.[RID]`, where `[RID]` represents the runtime identifier of the specific platform. For more information on runtime identifiers, see the official [RID catalog](https://learn.microsoft.com/en-us/dotnet/core/rid-catalog).

Supported platforms:

### Android

- android-arm
- android-arm64
- android-x64
- android-x86

### iOS

- ios-arm64
- iossimulator-arm64
- iossimulator-x64

### Linux

- linux-arm
- linux-arm64
- linux-loongarch64
- linux-musl-arm64
- linux-musl-x64
- linux-x64

### macOS

- osx
- osx-arm64
- osx-x64

### Windows

- win-arm64
- win-arm64-md
- win-x64
- win-x64-md
- win-x86
- win-x86-md

RID without a suffix uses the `/MT` multithreaded, static runtime library. The `-md` suffix identifies builds using `/MD`, the multithreaded DLL-specific runtime library.

For more information on the differences between `/MD` and `/MT`, refer to the official documentation: [/MD, /MT, /LD (Use runtime library)](https://learn.microsoft.com/en-us/cpp/build/reference/md-mt-ld-use-run-time-library?view=msvc-170).

## License

MIT

# OpenSSL App Test
A test project build for debugging openssl command line tool. Use unchanged code copied from libressl-2.6.2/apps folder.

# Build Steps
- **Build library of LibreSSL for MSVC**
  1. Install Visual Studio 2015
  2. Download LibreSSL source code. eg [libressl-2.6.2.tar.gz](https://ftp.openbsd.org/pub/OpenBSD/LibreSSL/libressl-2.6.2.tar.gz)
  3. Extract to path `X:/path/to/libressl-2.6.2`
  4. Open `cmake-gui.exe`, Set source and build path, Configure, Generate
  5. Open LibreSSL.sln, Build

- **Create OpenSSL app project**
  1. Create empty project in VS2015.
  2. Copy LibreSSL apps source and header file in path `X:/path/to/libressl-2.6.2/apps` to project folder.
  4. Config `Include path` and `Libary Path` in properties page.
  5. Add link library(static) `tls\Debug\tls.lib;ssl\Debug\ssl.lib;crypto\Debug\crypto.lib;ws2_32.lib;`
  6. Add PreprocessorDefinitions `OPENSSL_NO_SPEED`
  7. Build

# Dependency
[LibreSSL](https://www.libressl.org/) 2.6.2

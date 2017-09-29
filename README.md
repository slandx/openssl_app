# OpenSSL App Test
A test project build for debugging openssl command line tool. Use unchanged code copied from openssl/app folder and openssl/ms folder.

# Build Steps
- **Build static library of OpenSSL for MSVC**
  1. Install Visual Studio 2015
  2. Download OpenSSL source code. eg [openssl-1.1.0f.tar.gz](https://www.openssl.org/source/openssl-1.1.0f.tar.gz)
  3. Extract to path `C:/openssl-1.1.0f`
  4. Install [ActivePerl](http://www.activestate.com/activeperl/downloads)
  5. Open 'Visual Studio 2015 Command Prompt', and run command below:

```
perl Configure VC-WIN32 no-asm no-shared --prefix="C:/openssl-1.1.0f/win32-release"--openssldir="C:/openssl-1.1.0f/win32-release/ssl"
nmake
nmake test
make install
nmake clean
```

- **Create OpenSSL app project**
  1. Create empty project in VS2015.
  2. Copy OpenSSL app source code in path `C:/openssl-1.1.0f/app` to project folder.
  3. Copy OpenSSL ms source code in path `C:/openssl-1.1.0f/ms` to project folder.
  4. Config `Include path` and `Libary Path` in properties page.
  5. Add link library `libcrypto.lib;libssl.lib;ws2_32.lib;Crypt32.lib;`
  6. Add PreprocessorDefinitions `WIN32_LEAN_AND_MEAN`
  7. Build

# Dependency
OpenSSL 1.1.0f

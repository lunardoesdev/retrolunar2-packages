# Porting report

Every line the Lua→TOML port dropped, rewrote or flagged, per file.


## aarch64-android21/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD AS ASM STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `CXXFLAGS="$CXXFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_AARCH64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_AARCH64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_aarch64_linux_android CFLAGS_aarch64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_aarch64_linux_android CXXFLAGS_aarch64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `CXXFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@aarch64-android21/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@aarch64-android21/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@aarch64-android21/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@aarch64-android21/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@aarch64-android21/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## aarch64-android21/aarch64-linux-android21-toolchain.cmake

- **copied unchanged**: `aarch64-linux-android21-toolchain.cmake`

## aarch64-android21/crossfile-aarch64-android21.ini

- **copied unchanged**: `crossfile-aarch64-android21.ini`

## aarch64-android21/generic.lua

- **ported to**: `system@aarch64-android21`

## aarch64-android23/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD AS ASM STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `CXXFLAGS="$CXXFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_AARCH64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_AARCH64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_aarch64_linux_android CFLAGS_aarch64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_aarch64_linux_android CXXFLAGS_aarch64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `CXXFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@aarch64-android23/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@aarch64-android23/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@aarch64-android23/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@aarch64-android23/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@aarch64-android23/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## aarch64-android23/aarch64-linux-android23-toolchain.cmake

- **copied unchanged**: `aarch64-linux-android23-toolchain.cmake`

## aarch64-android23/crossfile-aarch64-android23.ini

- **copied unchanged**: `crossfile-aarch64-android23.ini`

## aarch64-android23/generic.lua

- **ported to**: `system@aarch64-android23`

## aarch64-android24/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD AS ASM STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `CXXFLAGS="$CXXFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_AARCH64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_AARCH64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_aarch64_linux_android CFLAGS_aarch64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_aarch64_linux_android CXXFLAGS_aarch64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `CXXFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@aarch64-android24/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@aarch64-android24/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@aarch64-android24/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@aarch64-android24/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@aarch64-android24/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## aarch64-android24/aarch64-linux-android24-toolchain.cmake

- **copied unchanged**: `aarch64-linux-android24-toolchain.cmake`

## aarch64-android24/crossfile-aarch64-android24.ini

- **copied unchanged**: `crossfile-aarch64-android24.ini`

## aarch64-android24/generic.lua

- **ported to**: `system@aarch64-android24`

## aarch64-android25/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD AS ASM STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `CXXFLAGS="$CXXFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_AARCH64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_AARCH64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_aarch64_linux_android CFLAGS_aarch64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_aarch64_linux_android CXXFLAGS_aarch64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `CXXFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@aarch64-android25/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@aarch64-android25/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@aarch64-android25/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@aarch64-android25/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@aarch64-android25/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## aarch64-android25/aarch64-linux-android25-toolchain.cmake

- **copied unchanged**: `aarch64-linux-android25-toolchain.cmake`

## aarch64-android25/crossfile-aarch64-android25.ini

- **copied unchanged**: `crossfile-aarch64-android25.ini`

## aarch64-android25/generic.lua

- **ported to**: `system@aarch64-android25`

## aarch64-android26/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD AS ASM STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `CXXFLAGS="$CXXFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_AARCH64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_AARCH64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_aarch64_linux_android CFLAGS_aarch64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_aarch64_linux_android CXXFLAGS_aarch64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `CXXFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@aarch64-android26/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@aarch64-android26/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@aarch64-android26/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@aarch64-android26/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@aarch64-android26/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## aarch64-android26/aarch64-linux-android26-toolchain.cmake

- **copied unchanged**: `aarch64-linux-android26-toolchain.cmake`

## aarch64-android26/crossfile-aarch64-android26.ini

- **copied unchanged**: `crossfile-aarch64-android26.ini`

## aarch64-android26/generic.lua

- **ported to**: `system@aarch64-android26`

## aarch64-android27/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD AS ASM STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `CXXFLAGS="$CXXFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_AARCH64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_AARCH64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_aarch64_linux_android CFLAGS_aarch64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_aarch64_linux_android CXXFLAGS_aarch64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `CXXFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@aarch64-android27/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@aarch64-android27/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@aarch64-android27/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@aarch64-android27/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@aarch64-android27/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## aarch64-android27/aarch64-linux-android27-toolchain.cmake

- **copied unchanged**: `aarch64-linux-android27-toolchain.cmake`

## aarch64-android27/crossfile-aarch64-android27.ini

- **copied unchanged**: `crossfile-aarch64-android27.ini`

## aarch64-android27/generic.lua

- **ported to**: `system@aarch64-android27`

## aarch64-android28/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD AS ASM STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `CXXFLAGS="$CXXFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_AARCH64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_AARCH64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_aarch64_linux_android CFLAGS_aarch64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_aarch64_linux_android CXXFLAGS_aarch64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `CXXFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@aarch64-android28/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@aarch64-android28/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@aarch64-android28/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@aarch64-android28/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@aarch64-android28/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## aarch64-android28/aarch64-linux-android28-toolchain.cmake

- **copied unchanged**: `aarch64-linux-android28-toolchain.cmake`

## aarch64-android28/crossfile-aarch64-android28.ini

- **copied unchanged**: `crossfile-aarch64-android28.ini`

## aarch64-android28/generic.lua

- **ported to**: `system@aarch64-android28`

## aarch64-android29/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD AS ASM STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `CXXFLAGS="$CXXFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_AARCH64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_AARCH64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_aarch64_linux_android CFLAGS_aarch64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_aarch64_linux_android CXXFLAGS_aarch64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `CXXFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@aarch64-android29/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@aarch64-android29/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@aarch64-android29/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@aarch64-android29/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@aarch64-android29/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## aarch64-android29/aarch64-linux-android29-toolchain.cmake

- **copied unchanged**: `aarch64-linux-android29-toolchain.cmake`

## aarch64-android29/crossfile-aarch64-android29.ini

- **copied unchanged**: `crossfile-aarch64-android29.ini`

## aarch64-android29/generic.lua

- **ported to**: `system@aarch64-android29`

## aarch64-android30/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD AS ASM STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `CXXFLAGS="$CXXFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_AARCH64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_AARCH64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_aarch64_linux_android CFLAGS_aarch64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_aarch64_linux_android CXXFLAGS_aarch64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `CXXFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@aarch64-android30/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@aarch64-android30/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@aarch64-android30/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@aarch64-android30/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@aarch64-android30/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## aarch64-android30/aarch64-linux-android30-toolchain.cmake

- **copied unchanged**: `aarch64-linux-android30-toolchain.cmake`

## aarch64-android30/crossfile-aarch64-android30.ini

- **copied unchanged**: `crossfile-aarch64-android30.ini`

## aarch64-android30/generic.lua

- **ported to**: `system@aarch64-android30`

## aarch64-android31/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD AS ASM STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `CXXFLAGS="$CXXFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_AARCH64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_AARCH64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_aarch64_linux_android CFLAGS_aarch64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_aarch64_linux_android CXXFLAGS_aarch64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `CXXFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@aarch64-android31/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@aarch64-android31/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@aarch64-android31/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@aarch64-android31/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@aarch64-android31/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## aarch64-android31/aarch64-linux-android31-toolchain.cmake

- **copied unchanged**: `aarch64-linux-android31-toolchain.cmake`

## aarch64-android31/crossfile-aarch64-android31.ini

- **copied unchanged**: `crossfile-aarch64-android31.ini`

## aarch64-android31/generic.lua

- **ported to**: `system@aarch64-android31`

## aarch64-android32/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD AS ASM STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `CXXFLAGS="$CXXFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_AARCH64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_AARCH64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_aarch64_linux_android CFLAGS_aarch64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_aarch64_linux_android CXXFLAGS_aarch64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `CXXFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@aarch64-android32/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@aarch64-android32/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@aarch64-android32/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@aarch64-android32/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@aarch64-android32/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## aarch64-android32/aarch64-linux-android32-toolchain.cmake

- **copied unchanged**: `aarch64-linux-android32-toolchain.cmake`

## aarch64-android32/crossfile-aarch64-android32.ini

- **copied unchanged**: `crossfile-aarch64-android32.ini`

## aarch64-android32/generic.lua

- **ported to**: `system@aarch64-android32`

## aarch64-android33/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD AS ASM STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `CXXFLAGS="$CXXFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_AARCH64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_AARCH64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_aarch64_linux_android CFLAGS_aarch64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_aarch64_linux_android CXXFLAGS_aarch64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `CXXFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@aarch64-android33/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@aarch64-android33/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@aarch64-android33/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@aarch64-android33/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@aarch64-android33/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## aarch64-android33/aarch64-linux-android33-toolchain.cmake

- **copied unchanged**: `aarch64-linux-android33-toolchain.cmake`

## aarch64-android33/crossfile-aarch64-android33.ini

- **copied unchanged**: `crossfile-aarch64-android33.ini`

## aarch64-android33/generic.lua

- **ported to**: `system@aarch64-android33`

## aarch64-android34/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD AS ASM STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `CXXFLAGS="$CXXFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_AARCH64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_AARCH64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_aarch64_linux_android CFLAGS_aarch64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_aarch64_linux_android CXXFLAGS_aarch64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `CXXFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@aarch64-android34/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@aarch64-android34/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@aarch64-android34/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@aarch64-android34/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@aarch64-android34/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## aarch64-android34/aarch64-linux-android34-toolchain.cmake

- **copied unchanged**: `aarch64-linux-android34-toolchain.cmake`

## aarch64-android34/crossfile-aarch64-android34.ini

- **copied unchanged**: `crossfile-aarch64-android34.ini`

## aarch64-android34/generic.lua

- **ported to**: `system@aarch64-android34`

## aarch64-android35/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD AS ASM STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `CXXFLAGS="$CXXFLAGS -I$PREFIX/include"`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_AARCH64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_AARCH64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_aarch64_linux_android CFLAGS_aarch64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_aarch64_linux_android CXXFLAGS_aarch64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `CXXFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@aarch64-android35/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@aarch64-android35/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@aarch64-android35/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@aarch64-android35/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@aarch64-android35/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## aarch64-android35/aarch64-linux-android35-toolchain.cmake

- **copied unchanged**: `aarch64-linux-android35-toolchain.cmake`

## aarch64-android35/crossfile-aarch64-android35.ini

- **copied unchanged**: `crossfile-aarch64-android35.ini`

## aarch64-android35/generic.lua

- **ported to**: `system@aarch64-android35`

## armv7a-android21/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_armv7_linux_androideabi CFLAGS_armv7_linux_androideabi`
- **dropped 'export' (variables are exported per file)**: `export CXX_armv7_linux_androideabi CXXFLAGS_armv7_linux_androideabi`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@armv7a-android21/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@armv7a-android21/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@armv7a-android21/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@armv7a-android21/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@armv7a-android21/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## armv7a-android21/armv7a-linux-androideabi21-toolchain.cmake

- **copied unchanged**: `armv7a-linux-androideabi21-toolchain.cmake`

## armv7a-android21/crossfile-armv7a-android21.ini

- **copied unchanged**: `crossfile-armv7a-android21.ini`

## armv7a-android21/generic.lua

- **ported to**: `system@armv7a-android21`

## armv7a-android23/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_armv7_linux_androideabi CFLAGS_armv7_linux_androideabi`
- **dropped 'export' (variables are exported per file)**: `export CXX_armv7_linux_androideabi CXXFLAGS_armv7_linux_androideabi`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@armv7a-android23/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@armv7a-android23/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@armv7a-android23/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@armv7a-android23/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@armv7a-android23/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## armv7a-android23/armv7a-linux-androideabi23-toolchain.cmake

- **copied unchanged**: `armv7a-linux-androideabi23-toolchain.cmake`

## armv7a-android23/crossfile-armv7a-android23.ini

- **copied unchanged**: `crossfile-armv7a-android23.ini`

## armv7a-android23/generic.lua

- **ported to**: `system@armv7a-android23`

## armv7a-android24/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_armv7_linux_androideabi CFLAGS_armv7_linux_androideabi`
- **dropped 'export' (variables are exported per file)**: `export CXX_armv7_linux_androideabi CXXFLAGS_armv7_linux_androideabi`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@armv7a-android24/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@armv7a-android24/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@armv7a-android24/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@armv7a-android24/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@armv7a-android24/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## armv7a-android24/armv7a-linux-androideabi24-toolchain.cmake

- **copied unchanged**: `armv7a-linux-androideabi24-toolchain.cmake`

## armv7a-android24/crossfile-armv7a-android24.ini

- **copied unchanged**: `crossfile-armv7a-android24.ini`

## armv7a-android24/generic.lua

- **ported to**: `system@armv7a-android24`

## armv7a-android25/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_armv7_linux_androideabi CFLAGS_armv7_linux_androideabi`
- **dropped 'export' (variables are exported per file)**: `export CXX_armv7_linux_androideabi CXXFLAGS_armv7_linux_androideabi`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@armv7a-android25/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@armv7a-android25/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@armv7a-android25/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@armv7a-android25/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@armv7a-android25/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## armv7a-android25/armv7a-linux-androideabi25-toolchain.cmake

- **copied unchanged**: `armv7a-linux-androideabi25-toolchain.cmake`

## armv7a-android25/crossfile-armv7a-android25.ini

- **copied unchanged**: `crossfile-armv7a-android25.ini`

## armv7a-android25/generic.lua

- **ported to**: `system@armv7a-android25`

## armv7a-android26/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_armv7_linux_androideabi CFLAGS_armv7_linux_androideabi`
- **dropped 'export' (variables are exported per file)**: `export CXX_armv7_linux_androideabi CXXFLAGS_armv7_linux_androideabi`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@armv7a-android26/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@armv7a-android26/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@armv7a-android26/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@armv7a-android26/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@armv7a-android26/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## armv7a-android26/armv7a-linux-androideabi26-toolchain.cmake

- **copied unchanged**: `armv7a-linux-androideabi26-toolchain.cmake`

## armv7a-android26/crossfile-armv7a-android26.ini

- **copied unchanged**: `crossfile-armv7a-android26.ini`

## armv7a-android26/generic.lua

- **ported to**: `system@armv7a-android26`

## armv7a-android27/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_armv7_linux_androideabi CFLAGS_armv7_linux_androideabi`
- **dropped 'export' (variables are exported per file)**: `export CXX_armv7_linux_androideabi CXXFLAGS_armv7_linux_androideabi`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@armv7a-android27/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@armv7a-android27/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@armv7a-android27/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@armv7a-android27/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@armv7a-android27/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## armv7a-android27/armv7a-linux-androideabi27-toolchain.cmake

- **copied unchanged**: `armv7a-linux-androideabi27-toolchain.cmake`

## armv7a-android27/crossfile-armv7a-android27.ini

- **copied unchanged**: `crossfile-armv7a-android27.ini`

## armv7a-android27/generic.lua

- **ported to**: `system@armv7a-android27`

## armv7a-android28/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_armv7_linux_androideabi CFLAGS_armv7_linux_androideabi`
- **dropped 'export' (variables are exported per file)**: `export CXX_armv7_linux_androideabi CXXFLAGS_armv7_linux_androideabi`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@armv7a-android28/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@armv7a-android28/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@armv7a-android28/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@armv7a-android28/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@armv7a-android28/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## armv7a-android28/armv7a-linux-androideabi28-toolchain.cmake

- **copied unchanged**: `armv7a-linux-androideabi28-toolchain.cmake`

## armv7a-android28/crossfile-armv7a-android28.ini

- **copied unchanged**: `crossfile-armv7a-android28.ini`

## armv7a-android28/generic.lua

- **ported to**: `system@armv7a-android28`

## armv7a-android29/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_armv7_linux_androideabi CFLAGS_armv7_linux_androideabi`
- **dropped 'export' (variables are exported per file)**: `export CXX_armv7_linux_androideabi CXXFLAGS_armv7_linux_androideabi`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@armv7a-android29/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@armv7a-android29/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@armv7a-android29/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@armv7a-android29/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@armv7a-android29/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## armv7a-android29/armv7a-linux-androideabi29-toolchain.cmake

- **copied unchanged**: `armv7a-linux-androideabi29-toolchain.cmake`

## armv7a-android29/crossfile-armv7a-android29.ini

- **copied unchanged**: `crossfile-armv7a-android29.ini`

## armv7a-android29/generic.lua

- **ported to**: `system@armv7a-android29`

## armv7a-android30/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_armv7_linux_androideabi CFLAGS_armv7_linux_androideabi`
- **dropped 'export' (variables are exported per file)**: `export CXX_armv7_linux_androideabi CXXFLAGS_armv7_linux_androideabi`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@armv7a-android30/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@armv7a-android30/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@armv7a-android30/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@armv7a-android30/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@armv7a-android30/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## armv7a-android30/armv7a-linux-androideabi30-toolchain.cmake

- **copied unchanged**: `armv7a-linux-androideabi30-toolchain.cmake`

## armv7a-android30/crossfile-armv7a-android30.ini

- **copied unchanged**: `crossfile-armv7a-android30.ini`

## armv7a-android30/generic.lua

- **ported to**: `system@armv7a-android30`

## armv7a-android31/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_armv7_linux_androideabi CFLAGS_armv7_linux_androideabi`
- **dropped 'export' (variables are exported per file)**: `export CXX_armv7_linux_androideabi CXXFLAGS_armv7_linux_androideabi`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@armv7a-android31/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@armv7a-android31/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@armv7a-android31/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@armv7a-android31/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@armv7a-android31/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## armv7a-android31/armv7a-linux-androideabi31-toolchain.cmake

- **copied unchanged**: `armv7a-linux-androideabi31-toolchain.cmake`

## armv7a-android31/crossfile-armv7a-android31.ini

- **copied unchanged**: `crossfile-armv7a-android31.ini`

## armv7a-android31/generic.lua

- **ported to**: `system@armv7a-android31`

## armv7a-android32/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_armv7_linux_androideabi CFLAGS_armv7_linux_androideabi`
- **dropped 'export' (variables are exported per file)**: `export CXX_armv7_linux_androideabi CXXFLAGS_armv7_linux_androideabi`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@armv7a-android32/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@armv7a-android32/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@armv7a-android32/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@armv7a-android32/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@armv7a-android32/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## armv7a-android32/armv7a-linux-androideabi32-toolchain.cmake

- **copied unchanged**: `armv7a-linux-androideabi32-toolchain.cmake`

## armv7a-android32/crossfile-armv7a-android32.ini

- **copied unchanged**: `crossfile-armv7a-android32.ini`

## armv7a-android32/generic.lua

- **ported to**: `system@armv7a-android32`

## armv7a-android33/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_armv7_linux_androideabi CFLAGS_armv7_linux_androideabi`
- **dropped 'export' (variables are exported per file)**: `export CXX_armv7_linux_androideabi CXXFLAGS_armv7_linux_androideabi`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@armv7a-android33/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@armv7a-android33/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@armv7a-android33/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@armv7a-android33/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@armv7a-android33/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## armv7a-android33/armv7a-linux-androideabi33-toolchain.cmake

- **copied unchanged**: `armv7a-linux-androideabi33-toolchain.cmake`

## armv7a-android33/crossfile-armv7a-android33.ini

- **copied unchanged**: `crossfile-armv7a-android33.ini`

## armv7a-android33/generic.lua

- **ported to**: `system@armv7a-android33`

## armv7a-android34/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_armv7_linux_androideabi CFLAGS_armv7_linux_androideabi`
- **dropped 'export' (variables are exported per file)**: `export CXX_armv7_linux_androideabi CXXFLAGS_armv7_linux_androideabi`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@armv7a-android34/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@armv7a-android34/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@armv7a-android34/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@armv7a-android34/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@armv7a-android34/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## armv7a-android34/armv7a-linux-androideabi34-toolchain.cmake

- **copied unchanged**: `armv7a-linux-androideabi34-toolchain.cmake`

## armv7a-android34/crossfile-armv7a-android34.ini

- **copied unchanged**: `crossfile-armv7a-android34.ini`

## armv7a-android34/generic.lua

- **ported to**: `system@armv7a-android34`

## armv7a-android35/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_ARMV7_LINUX_ANDROIDEABI_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_armv7_linux_androideabi CFLAGS_armv7_linux_androideabi`
- **dropped 'export' (variables are exported per file)**: `export CXX_armv7_linux_androideabi CXXFLAGS_armv7_linux_androideabi`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@armv7a-android35/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@armv7a-android35/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@armv7a-android35/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@armv7a-android35/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@armv7a-android35/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## armv7a-android35/armv7a-linux-androideabi35-toolchain.cmake

- **copied unchanged**: `armv7a-linux-androideabi35-toolchain.cmake`

## armv7a-android35/crossfile-armv7a-android35.ini

- **copied unchanged**: `crossfile-armv7a-android35.ini`

## armv7a-android35/generic.lua

- **ported to**: `system@armv7a-android35`

## clang-native/generic.lua

- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD AS STRIP OBJCOPY READELF OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS CFLAGS CXXFLAGS LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--build=$BUILD_TRIPLET --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `-DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_PREFIX_PATH CMAKE_FLAGS MESON_FLAGS`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `CXXFLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **added the cargo target v1 never defined**: `x86_64-unknown-linux-gnu`

## system@clang-native/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@clang-native/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@clang-native/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@clang-native/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@clang-native/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## clang-native/generic.lua

- **ported to**: `system@clang-native`

## i686-android21/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_I686_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_I686_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_i686_linux_android CFLAGS_i686_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_i686_linux_android CXXFLAGS_i686_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@i686-android21/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@i686-android21/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@i686-android21/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@i686-android21/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@i686-android21/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## i686-android21/crossfile-i686-android21.ini

- **copied unchanged**: `crossfile-i686-android21.ini`

## i686-android21/i686-linux-android21-toolchain.cmake

- **copied unchanged**: `i686-linux-android21-toolchain.cmake`

## i686-android21/generic.lua

- **ported to**: `system@i686-android21`

## i686-android23/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_I686_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_I686_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_i686_linux_android CFLAGS_i686_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_i686_linux_android CXXFLAGS_i686_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@i686-android23/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@i686-android23/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@i686-android23/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@i686-android23/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@i686-android23/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## i686-android23/crossfile-i686-android23.ini

- **copied unchanged**: `crossfile-i686-android23.ini`

## i686-android23/i686-linux-android23-toolchain.cmake

- **copied unchanged**: `i686-linux-android23-toolchain.cmake`

## i686-android23/generic.lua

- **ported to**: `system@i686-android23`

## i686-android24/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_I686_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_I686_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_i686_linux_android CFLAGS_i686_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_i686_linux_android CXXFLAGS_i686_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@i686-android24/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@i686-android24/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@i686-android24/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@i686-android24/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@i686-android24/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## i686-android24/crossfile-i686-android24.ini

- **copied unchanged**: `crossfile-i686-android24.ini`

## i686-android24/i686-linux-android24-toolchain.cmake

- **copied unchanged**: `i686-linux-android24-toolchain.cmake`

## i686-android24/generic.lua

- **ported to**: `system@i686-android24`

## i686-android25/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_I686_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_I686_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_i686_linux_android CFLAGS_i686_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_i686_linux_android CXXFLAGS_i686_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@i686-android25/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@i686-android25/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@i686-android25/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@i686-android25/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@i686-android25/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## i686-android25/crossfile-i686-android25.ini

- **copied unchanged**: `crossfile-i686-android25.ini`

## i686-android25/i686-linux-android25-toolchain.cmake

- **copied unchanged**: `i686-linux-android25-toolchain.cmake`

## i686-android25/generic.lua

- **ported to**: `system@i686-android25`

## i686-android26/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_I686_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_I686_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_i686_linux_android CFLAGS_i686_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_i686_linux_android CXXFLAGS_i686_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@i686-android26/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@i686-android26/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@i686-android26/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@i686-android26/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@i686-android26/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## i686-android26/crossfile-i686-android26.ini

- **copied unchanged**: `crossfile-i686-android26.ini`

## i686-android26/i686-linux-android26-toolchain.cmake

- **copied unchanged**: `i686-linux-android26-toolchain.cmake`

## i686-android26/generic.lua

- **ported to**: `system@i686-android26`

## i686-android27/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_I686_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_I686_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_i686_linux_android CFLAGS_i686_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_i686_linux_android CXXFLAGS_i686_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@i686-android27/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@i686-android27/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@i686-android27/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@i686-android27/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@i686-android27/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## i686-android27/crossfile-i686-android27.ini

- **copied unchanged**: `crossfile-i686-android27.ini`

## i686-android27/i686-linux-android27-toolchain.cmake

- **copied unchanged**: `i686-linux-android27-toolchain.cmake`

## i686-android27/generic.lua

- **ported to**: `system@i686-android27`

## i686-android28/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_I686_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_I686_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_i686_linux_android CFLAGS_i686_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_i686_linux_android CXXFLAGS_i686_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@i686-android28/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@i686-android28/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@i686-android28/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@i686-android28/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@i686-android28/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## i686-android28/crossfile-i686-android28.ini

- **copied unchanged**: `crossfile-i686-android28.ini`

## i686-android28/i686-linux-android28-toolchain.cmake

- **copied unchanged**: `i686-linux-android28-toolchain.cmake`

## i686-android28/generic.lua

- **ported to**: `system@i686-android28`

## i686-android29/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_I686_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_I686_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_i686_linux_android CFLAGS_i686_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_i686_linux_android CXXFLAGS_i686_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@i686-android29/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@i686-android29/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@i686-android29/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@i686-android29/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@i686-android29/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## i686-android29/crossfile-i686-android29.ini

- **copied unchanged**: `crossfile-i686-android29.ini`

## i686-android29/i686-linux-android29-toolchain.cmake

- **copied unchanged**: `i686-linux-android29-toolchain.cmake`

## i686-android29/generic.lua

- **ported to**: `system@i686-android29`

## i686-android30/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_I686_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_I686_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_i686_linux_android CFLAGS_i686_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_i686_linux_android CXXFLAGS_i686_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@i686-android30/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@i686-android30/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@i686-android30/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@i686-android30/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@i686-android30/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## i686-android30/crossfile-i686-android30.ini

- **copied unchanged**: `crossfile-i686-android30.ini`

## i686-android30/i686-linux-android30-toolchain.cmake

- **copied unchanged**: `i686-linux-android30-toolchain.cmake`

## i686-android30/generic.lua

- **ported to**: `system@i686-android30`

## i686-android31/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_I686_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_I686_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_i686_linux_android CFLAGS_i686_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_i686_linux_android CXXFLAGS_i686_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@i686-android31/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@i686-android31/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@i686-android31/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@i686-android31/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@i686-android31/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## i686-android31/crossfile-i686-android31.ini

- **copied unchanged**: `crossfile-i686-android31.ini`

## i686-android31/i686-linux-android31-toolchain.cmake

- **copied unchanged**: `i686-linux-android31-toolchain.cmake`

## i686-android31/generic.lua

- **ported to**: `system@i686-android31`

## i686-android32/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_I686_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_I686_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_i686_linux_android CFLAGS_i686_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_i686_linux_android CXXFLAGS_i686_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@i686-android32/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@i686-android32/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@i686-android32/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@i686-android32/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@i686-android32/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## i686-android32/crossfile-i686-android32.ini

- **copied unchanged**: `crossfile-i686-android32.ini`

## i686-android32/i686-linux-android32-toolchain.cmake

- **copied unchanged**: `i686-linux-android32-toolchain.cmake`

## i686-android32/generic.lua

- **ported to**: `system@i686-android32`

## i686-android33/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_I686_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_I686_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_i686_linux_android CFLAGS_i686_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_i686_linux_android CXXFLAGS_i686_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@i686-android33/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@i686-android33/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@i686-android33/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@i686-android33/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@i686-android33/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## i686-android33/crossfile-i686-android33.ini

- **copied unchanged**: `crossfile-i686-android33.ini`

## i686-android33/i686-linux-android33-toolchain.cmake

- **copied unchanged**: `i686-linux-android33-toolchain.cmake`

## i686-android33/generic.lua

- **ported to**: `system@i686-android33`

## i686-android34/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_I686_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_I686_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_i686_linux_android CFLAGS_i686_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_i686_linux_android CXXFLAGS_i686_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@i686-android34/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@i686-android34/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@i686-android34/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@i686-android34/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@i686-android34/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## i686-android34/crossfile-i686-android34.ini

- **copied unchanged**: `crossfile-i686-android34.ini`

## i686-android34/i686-linux-android34-toolchain.cmake

- **copied unchanged**: `i686-linux-android34-toolchain.cmake`

## i686-android34/generic.lua

- **ported to**: `system@i686-android34`

## i686-android35/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_I686_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_I686_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_i686_linux_android CFLAGS_i686_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_i686_linux_android CXXFLAGS_i686_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@i686-android35/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@i686-android35/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@i686-android35/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@i686-android35/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@i686-android35/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## i686-android35/crossfile-i686-android35.ini

- **copied unchanged**: `crossfile-i686-android35.ini`

## i686-android35/i686-linux-android35-toolchain.cmake

- **copied unchanged**: `i686-linux-android35-toolchain.cmake`

## i686-android35/generic.lua

- **ported to**: `system@i686-android35`

## mingw32/generic.lua

- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP WINDRES`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **FLAGGED $PREFIX in a system fragment**: `$CMAKE_FLAGS -DZLIB_ROOT=$PREFIX`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`

## mingw32/cmake.toml

- **fixed by hand (CMAKE_PREFIX_PATH from the closure points at the dependency directories already)**: `-DZLIB_ROOT=\$\{RETROLUNAR_PORT_SYSTEM_PREFIX\}`

## mingw32/generic.lua

- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@mingw32/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@mingw32/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@mingw32/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@mingw32/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@mingw32/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## mingw32/crossfile-i686-w64-mingw32.ini

- **copied unchanged**: `crossfile-i686-w64-mingw32.ini`

## mingw32/i686-w64-mingw32-toolchain.cmake

- **copied unchanged**: `i686-w64-mingw32-toolchain.cmake`

## mingw32/generic.lua

- **ported to**: `system@mingw32`

## x86_64-android21/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_X86_64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_X86_64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_x86_64_linux_android CFLAGS_x86_64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_x86_64_linux_android CXXFLAGS_x86_64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@x86_64-android21/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@x86_64-android21/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@x86_64-android21/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@x86_64-android21/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@x86_64-android21/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## x86_64-android21/crossfile-x86_64-android21.ini

- **copied unchanged**: `crossfile-x86_64-android21.ini`

## x86_64-android21/x86_64-linux-android21-toolchain.cmake

- **copied unchanged**: `x86_64-linux-android21-toolchain.cmake`

## x86_64-android21/generic.lua

- **ported to**: `system@x86_64-android21`

## x86_64-android23/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_X86_64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_X86_64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_x86_64_linux_android CFLAGS_x86_64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_x86_64_linux_android CXXFLAGS_x86_64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@x86_64-android23/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@x86_64-android23/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@x86_64-android23/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@x86_64-android23/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@x86_64-android23/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## x86_64-android23/crossfile-x86_64-android23.ini

- **copied unchanged**: `crossfile-x86_64-android23.ini`

## x86_64-android23/x86_64-linux-android23-toolchain.cmake

- **copied unchanged**: `x86_64-linux-android23-toolchain.cmake`

## x86_64-android23/generic.lua

- **ported to**: `system@x86_64-android23`

## x86_64-android24/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_X86_64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_X86_64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_x86_64_linux_android CFLAGS_x86_64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_x86_64_linux_android CXXFLAGS_x86_64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@x86_64-android24/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@x86_64-android24/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@x86_64-android24/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@x86_64-android24/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@x86_64-android24/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## x86_64-android24/crossfile-x86_64-android24.ini

- **copied unchanged**: `crossfile-x86_64-android24.ini`

## x86_64-android24/x86_64-linux-android24-toolchain.cmake

- **copied unchanged**: `x86_64-linux-android24-toolchain.cmake`

## x86_64-android24/generic.lua

- **ported to**: `system@x86_64-android24`

## x86_64-android25/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_X86_64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_X86_64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_x86_64_linux_android CFLAGS_x86_64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_x86_64_linux_android CXXFLAGS_x86_64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@x86_64-android25/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@x86_64-android25/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@x86_64-android25/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@x86_64-android25/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@x86_64-android25/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## x86_64-android25/crossfile-x86_64-android25.ini

- **copied unchanged**: `crossfile-x86_64-android25.ini`

## x86_64-android25/x86_64-linux-android25-toolchain.cmake

- **copied unchanged**: `x86_64-linux-android25-toolchain.cmake`

## x86_64-android25/generic.lua

- **ported to**: `system@x86_64-android25`

## x86_64-android26/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_X86_64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_X86_64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_x86_64_linux_android CFLAGS_x86_64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_x86_64_linux_android CXXFLAGS_x86_64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@x86_64-android26/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@x86_64-android26/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@x86_64-android26/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@x86_64-android26/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@x86_64-android26/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## x86_64-android26/crossfile-x86_64-android26.ini

- **copied unchanged**: `crossfile-x86_64-android26.ini`

## x86_64-android26/x86_64-linux-android26-toolchain.cmake

- **copied unchanged**: `x86_64-linux-android26-toolchain.cmake`

## x86_64-android26/generic.lua

- **ported to**: `system@x86_64-android26`

## x86_64-android27/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_X86_64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_X86_64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_x86_64_linux_android CFLAGS_x86_64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_x86_64_linux_android CXXFLAGS_x86_64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@x86_64-android27/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@x86_64-android27/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@x86_64-android27/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@x86_64-android27/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@x86_64-android27/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## x86_64-android27/crossfile-x86_64-android27.ini

- **copied unchanged**: `crossfile-x86_64-android27.ini`

## x86_64-android27/x86_64-linux-android27-toolchain.cmake

- **copied unchanged**: `x86_64-linux-android27-toolchain.cmake`

## x86_64-android27/generic.lua

- **ported to**: `system@x86_64-android27`

## x86_64-android28/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_X86_64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_X86_64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_x86_64_linux_android CFLAGS_x86_64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_x86_64_linux_android CXXFLAGS_x86_64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@x86_64-android28/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@x86_64-android28/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@x86_64-android28/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@x86_64-android28/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@x86_64-android28/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## x86_64-android28/crossfile-x86_64-android28.ini

- **copied unchanged**: `crossfile-x86_64-android28.ini`

## x86_64-android28/x86_64-linux-android28-toolchain.cmake

- **copied unchanged**: `x86_64-linux-android28-toolchain.cmake`

## x86_64-android28/generic.lua

- **ported to**: `system@x86_64-android28`

## x86_64-android29/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_X86_64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_X86_64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_x86_64_linux_android CFLAGS_x86_64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_x86_64_linux_android CXXFLAGS_x86_64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@x86_64-android29/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@x86_64-android29/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@x86_64-android29/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@x86_64-android29/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@x86_64-android29/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## x86_64-android29/crossfile-x86_64-android29.ini

- **copied unchanged**: `crossfile-x86_64-android29.ini`

## x86_64-android29/x86_64-linux-android29-toolchain.cmake

- **copied unchanged**: `x86_64-linux-android29-toolchain.cmake`

## x86_64-android29/generic.lua

- **ported to**: `system@x86_64-android29`

## x86_64-android30/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_X86_64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_X86_64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_x86_64_linux_android CFLAGS_x86_64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_x86_64_linux_android CXXFLAGS_x86_64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@x86_64-android30/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@x86_64-android30/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@x86_64-android30/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@x86_64-android30/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@x86_64-android30/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## x86_64-android30/crossfile-x86_64-android30.ini

- **copied unchanged**: `crossfile-x86_64-android30.ini`

## x86_64-android30/x86_64-linux-android30-toolchain.cmake

- **copied unchanged**: `x86_64-linux-android30-toolchain.cmake`

## x86_64-android30/generic.lua

- **ported to**: `system@x86_64-android30`

## x86_64-android31/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_X86_64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_X86_64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_x86_64_linux_android CFLAGS_x86_64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_x86_64_linux_android CXXFLAGS_x86_64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@x86_64-android31/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@x86_64-android31/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@x86_64-android31/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@x86_64-android31/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@x86_64-android31/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## x86_64-android31/crossfile-x86_64-android31.ini

- **copied unchanged**: `crossfile-x86_64-android31.ini`

## x86_64-android31/x86_64-linux-android31-toolchain.cmake

- **copied unchanged**: `x86_64-linux-android31-toolchain.cmake`

## x86_64-android31/generic.lua

- **ported to**: `system@x86_64-android31`

## x86_64-android32/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_X86_64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_X86_64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_x86_64_linux_android CFLAGS_x86_64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_x86_64_linux_android CXXFLAGS_x86_64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@x86_64-android32/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@x86_64-android32/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@x86_64-android32/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@x86_64-android32/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@x86_64-android32/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## x86_64-android32/crossfile-x86_64-android32.ini

- **copied unchanged**: `crossfile-x86_64-android32.ini`

## x86_64-android32/x86_64-linux-android32-toolchain.cmake

- **copied unchanged**: `x86_64-linux-android32-toolchain.cmake`

## x86_64-android32/generic.lua

- **ported to**: `system@x86_64-android32`

## x86_64-android33/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_X86_64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_X86_64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_x86_64_linux_android CFLAGS_x86_64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_x86_64_linux_android CXXFLAGS_x86_64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@x86_64-android33/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@x86_64-android33/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@x86_64-android33/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@x86_64-android33/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@x86_64-android33/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## x86_64-android33/crossfile-x86_64-android33.ini

- **copied unchanged**: `crossfile-x86_64-android33.ini`

## x86_64-android33/x86_64-linux-android33-toolchain.cmake

- **copied unchanged**: `x86_64-linux-android33-toolchain.cmake`

## x86_64-android33/generic.lua

- **ported to**: `system@x86_64-android33`

## x86_64-android34/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_X86_64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_X86_64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_x86_64_linux_android CFLAGS_x86_64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_x86_64_linux_android CXXFLAGS_x86_64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@x86_64-android34/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@x86_64-android34/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@x86_64-android34/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@x86_64-android34/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@x86_64-android34/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## x86_64-android34/crossfile-x86_64-android34.ini

- **copied unchanged**: `crossfile-x86_64-android34.ini`

## x86_64-android34/x86_64-linux-android34-toolchain.cmake

- **copied unchanged**: `x86_64-linux-android34-toolchain.cmake`

## x86_64-android34/generic.lua

- **ported to**: `system@x86_64-android34`

## x86_64-android35/generic.lua

- **dropped 'export' (variables are exported per file)**: `export NDK`
- **dropped 'export' (variables are exported per file)**: `export TOOLCHAIN`
- **dropped 'export' (variables are exported per file)**: `export TOOLBIN`
- **dropped 'export' (variables are exported per file)**: `export SYSROOT`
- **dropped 'export' (variables are exported per file)**: `export ANDROID_API`
- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **kept an exported assignment (v2 exports every variable)**: `ac_cv_func_ffsl=yes`
- **kept an exported assignment (v2 exports every variable)**: `gl_cv_func_strcasecmp_works=yes`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_X86_64_LINUX_ANDROID_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_X86_64_LINUX_ANDROID_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_x86_64_linux_android CFLAGS_x86_64_linux_android`
- **dropped 'export' (variables are exported per file)**: `export CXX_x86_64_linux_android CXXFLAGS_x86_64_linux_android`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `CFLAGS`
- **merged repeated assignments**: `LDFLAGS`
- **merged repeated assignments**: `PKG_CONFIG_LIBDIR`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`
- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@x86_64-android35/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@x86_64-android35/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@x86_64-android35/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@x86_64-android35/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@x86_64-android35/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## x86_64-android35/crossfile-x86_64-android35.ini

- **copied unchanged**: `crossfile-x86_64-android35.ini`

## x86_64-android35/x86_64-linux-android35-toolchain.cmake

- **copied unchanged**: `x86_64-linux-android35-toolchain.cmake`

## x86_64-android35/generic.lua

- **ported to**: `system@x86_64-android35`

## mingw64/generic.lua

- **dropped 'export' (variables are exported per file)**: `export CC CXX AR RANLIB LD STRIP OBJCOPY READELF NM OBJDUMP WINDRES`
- **dropped (closure provides it)**: `CPPFLAGS="-I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CPPFLAGS`
- **dropped (closure provides it)**: `CFLAGS="$CFLAGS -I$PREFIX/include"`
- **dropped 'export' (variables are exported per file)**: `export CFLAGS CXXFLAGS`
- **dropped (closure provides it)**: `LDFLAGS="-L$PREFIX/lib"`
- **dropped (closure provides it)**: `LDFLAGS="$LDFLAGS -Wl,-rpath-link,$PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export LDFLAGS`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PREFIX/lib/pkgconfig"`
- **dropped (closure provides it)**: `PKG_CONFIG_LIBDIR="$PKG_CONFIG_LIBDIR:$PREFIX/share/pkgconfig"`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_LIBDIR PKG_CONFIG_PATH`
- **dropped 'export' (variables are exported per file)**: `export BUILD_TRIPLET HOST_TRIPLET TARGET_TRIPLET HOST_ARCH HOST_OS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$AUTOCONF_CONFIGURE_FLAGS --prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export AUTOCONF_CONFIGURE_FLAGS`
- **dropped (closure provides it)**: `CMAKE_PREFIX_PATH="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `$CMAKE_FLAGS -DCMAKE_INSTALL_PREFIX=$OUT`
- **dropped (closure provides it)**: `CMAKE_FLAGS="$CMAKE_FLAGS -DCMAKE_PREFIX_PATH=$PREFIX"`
- **made a tool lookup survive set -e**: `$(command -v make)`
- **FLAGGED $PREFIX in a system fragment**: `$CMAKE_FLAGS -DZLIB_ROOT=$PREFIX`
- **dropped 'export' (variables are exported per file)**: `export CMAKE_TOOLCHAIN_FILE CMAKE_PREFIX_PATH CMAKE_FLAGS`
- **rewrote $OUT to $OUTPKG (install prefix)**: `--prefix=$OUT`
- **dropped 'export' (variables are exported per file)**: `export MESON_CROSS_FILE MESON_FLAGS`
- **dropped (closure provides it)**: `RUSTFLAGS="-L $PREFIX/lib"`
- **dropped 'export' (variables are exported per file)**: `export CARGO_BUILD_TARGET CARGO_TARGET_X86_64_PC_WINDOWS_GNU_LINKER`
- **dropped 'export' (variables are exported per file)**: `export CARGO_TARGET_X86_64_PC_WINDOWS_GNU_AR RUSTFLAGS`
- **dropped 'export' (variables are exported per file)**: `export PKG_CONFIG_ALLOW_CROSS`
- **dropped 'export' (variables are exported per file)**: `export CC_x86_64_pc_windows_gnu CFLAGS_x86_64_pc_windows_gnu`
- **dropped 'export' (variables are exported per file)**: `export CXX_x86_64_pc_windows_gnu CXXFLAGS_x86_64_pc_windows_gnu`
- **dropped CORES (the emitter exports it)**: `CORES="${CORES:-1}"`
- **dropped 'export' (variables are exported per file)**: `export CORES MAKEFLAGS`
- **merged repeated assignments**: `AUTOCONF_CONFIGURE_FLAGS`

## mingw64/cmake.toml

- **fixed by hand (CMAKE_PREFIX_PATH from the closure points at the dependency directories already)**: `-DZLIB_ROOT=\$\{RETROLUNAR_PORT_SYSTEM_PREFIX\}`

## mingw64/generic.lua

- **merged repeated assignments**: `CMAKE_FLAGS`
- **merged repeated assignments**: `MESON_FLAGS`

## system@mingw64/autoconf.toml

- **carries the autoconf driver**: `script + defaults, overridable by this system`

## system@mingw64/cargo.toml

- **carries the cargo driver**: `script + defaults, overridable by this system`

## system@mingw64/cmake.toml

- **carries the cmake driver**: `script + defaults, overridable by this system`

## system@mingw64/make.toml

- **carries the make driver**: `script + defaults, overridable by this system`

## system@mingw64/meson.toml

- **carries the meson driver**: `script + defaults, overridable by this system`

## mingw64/crossfile-x86_64-mingw.ini

- **renamed with the system**: `crossfile-mingw64.ini`
- **copied unchanged**: `crossfile-x86_64-mingw.ini`

## mingw64/x86_64-w64-mingw32-toolchain.cmake

- **copied unchanged**: `x86_64-w64-mingw32-toolchain.cmake`

## mingw64/generic.lua

- **ported to**: `system@mingw64`

# Porting report

Every line the Lua→TOML port dropped, rewrote or flagged, per file.


## CGAL/source.lua

- **ported**: `source.toml`

## Eigen/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/Eigen@source/* .`
- **driven by the cmake build system**: `args=['-DEIGEN_BUILD_TESTING=OFF', '-DEIGEN_BUILD_DOC=OFF', '-DEIGEN_BUILD_DEMOS=OFF', '-DEIGEN_BUILD_BLAS=OFF', '-DEIGEN_BUILD_LAPACK=OFF', '-DEIGEN_BUILD_BTL=OFF', '-DEIGEN_BUILD_SPBENCH=OFF', '-DEI`
- **ported**: `generic.toml`

## Eigen/source.lua

- **ported**: `source.toml`

## Google-Benchmark/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/Google-Benchmark@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DBENCHMARK_ENABLE_TESTING=OFF']`
- **ported**: `generic.toml`

## Google-Benchmark/source.lua

- **ported**: `source.toml`

## Lexbor/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `awk '{ if ($0 ~ /^Libs:/) print "Libs: -L${libdir} -llexbor_static"; else print }' "$OUT/lib/pkgconfig/lexbor.pc" > "$WORK/lexbor.pc"`
- **rewrote $OUT to $PREFIX (staging)**: `cp "$WORK/lexbor.pc" "$OUT/lib/pkgconfig/lexbor.pc"`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/Lexbor@source/* .`
- **driven by the cmake build system**: `args=['-DLEXBOR_BUILD_SHARED=OFF']`
- **ported**: `generic.toml`

## Lexbor/source.lua

- **ported**: `source.toml`

## OpenAL-Soft/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/OpenAL-Soft@source/* .`
- **driven by the cmake build system**: `args=['-DLIBTYPE=STATIC', '-DALSOFT_UTILS=OFF', '-DALSOFT_EXAMPLES=OFF', '-DALSOFT_INSTALL_EXAMPLES=OFF', '-DALSOFT_INSTALL_UTILS=OFF', '-DALSOFT_INSTALL_CONFIG=OFF', '-DALSOFT_BUILD_IMPORT_LIB=OFF', `
- **ported**: `generic.toml`

## OpenAL-Soft/source.lua

- **ported**: `source.toml`

## SpeexDSP/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/SpeexDSP@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-static', '--disable-shared', '--with-pic', '--disable-examples']`
- **ported**: `generic.toml`

## SpeexDSP/source.lua

- **ported**: `source.toml`

## SuiteSparse/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/SuiteSparse@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DBUILD_STATIC_LIBS=ON', '-DSUITESPARSE_ENABLE_PROJECTS=suitesparse_config;btf;amd;camd;ccolamd;colamd;cholmod;cxsparse;klu;ldl;mongoose;rbio;spex', '-DSUITESPARSE_RE`
- **ported**: `generic.toml`

## SuiteSparse/source.lua

- **ported**: `source.toml`

## abseil-cpp/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/abseil-cpp@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DABSL_BUILD_TESTING=OFF']`
- **ported**: `generic.toml`

## abseil-cpp/source.lua

- **ported**: `source.toml`

## acl/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/acl@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## acl/source.lua

- **ported**: `source.toml`

## armadillo/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/armadillo@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF']`
- **ported**: `generic.toml`

## armadillo/source.lua

- **ported**: `source.toml`

## astyle/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/astyle@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF']`
- **ported**: `generic.toml`

## astyle/source.lua

- **ported**: `source.toml`

## attr/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/attr@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## attr/source.lua

- **ported**: `source.toml`

## autoconf/generic.lua

- **FLAGGED $PREFIX meaning dependencies**: `./configure $AUTOCONF_CONFIGURE_FLAGS --prefix="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `make -j"$CORES" prefix="$OUT" install`

## autoconf/generic.toml

- **fixed by hand (AUTOCONF_CONFIGURE_FLAGS already carries --prefix=$OUTPKG)**: `--prefix="\$\{RETROLUNAR_PORT_PREFIX\}"`

## autoconf/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/autoconf@source/* .`
- **driven by the autoconf build system**: `make=False, install=False`
- **ported**: `generic.toml`

## autoconf/source.lua

- **ported**: `source.toml`

## automake/generic.lua

- **FLAGGED $PREFIX meaning dependencies**: `./configure $AUTOCONF_CONFIGURE_FLAGS --prefix="$PREFIX"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `make -j"$CORES" prefix="$OUT" install`

## automake/generic.toml

- **fixed by hand (AUTOCONF_CONFIGURE_FLAGS already carries --prefix=$OUTPKG)**: `--prefix="\$\{RETROLUNAR_PORT_PREFIX\}"`

## automake/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/automake@source/* .`
- **driven by the autoconf build system**: `make=False, install=False`
- **ported**: `generic.toml`

## automake/source.lua

- **ported**: `source.toml`

## bash/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/bash@source/* .`
- **driven by the make build system**: `no arguments`
- **ported**: `generic.toml`

## bash/source.lua

- **ported**: `source.toml`

## bc/android.lua

- **rewrote $OUT to $OUTPKG (install prefix)**: `CC="$CC -std=c99" HOSTCC="cc" HOSTCFLAGS="-std=c99" ./configure --prefix="$OUT" --enable-readline --disable-nls`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/bc@source/* .`
- **driven by the make build system**: `make=False, install=False`
- **ported**: `android.toml`

## bc/generic.lua

- **rewrote $OUT to $OUTPKG (install prefix)**: `CC="$CC -std=c99" ./configure --prefix="$OUT" --enable-readline`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/bc@source/* .`
- **driven by the make build system**: `make=False, install=False`
- **ported**: `generic.toml`

## bc/source.lua

- **ported**: `source.toml`

## bear/clang-native.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/bear@source/* .`
- **driven by the cmake build system**: `args=['-DENABLE_UNIT_TESTS=OFF', '-DENABLE_FUNC_TESTS=OFF']`
- **ported**: `clang-native.toml`

## bear/source.lua

- **ported**: `source.toml`

## binutils/android.lua

- **rewrote $OUT to $OUTPKG (install prefix)**: `make -j"$CORES" tooldir="$OUT"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `make -j"$CORES" tooldir="$OUT" install`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/binutils@source/* .`
- **driven by the autoconf build system**: `make=False, install=False, configure_args=['--enable-ld=default', '--enable-plugins', '--enable-shared', '--disable-werror', '--enable-64-bit-bfd', '--enable-new-dtags', '--with-system-zlib', '--disab`
- **ported**: `android.toml`

## binutils/generic.lua

- **rewrote $OUT to $OUTPKG (install prefix)**: `make -j"$CORES" tooldir="$OUT"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `make -j"$CORES" tooldir="$OUT" install`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/binutils@source/* .`
- **driven by the autoconf build system**: `make=False, install=False, configure_args=['--enable-ld=default', '--enable-plugins', '--enable-shared', '--disable-werror', '--enable-64-bit-bfd', '--enable-new-dtags', '--with-system-zlib', '--enabl`
- **ported**: `generic.toml`

## binutils/source.lua

- **ported**: `source.toml`

## bison/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/bison@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-relocatable']`
- **ported**: `generic.toml`

## bison/source.lua

- **ported**: `source.toml`

## CMakeLists.txt

- **copied unchanged**: `CMakeLists.txt`

## boost/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/boost@source/* .`
- **driven by the cmake build system**: `no arguments`
- **ported**: `generic.toml`

## boost/source.lua

- **ported**: `source.toml`

## brotli/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/brotli@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF']`
- **ported**: `generic.toml`

## brotli/source.lua

- **ported**: `source.toml`

## bzip2/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `make -j"$CORES" CC="$CC" AR="$AR" RANLIB="$RANLIB" CFLAGS="$CFLAGS" LDFLAGS="$LDFLAGS" PREFIX="$OUT" install`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/bzip2@source/* .`
- **driven by the make build system**: `make=False, install=False, make_args=['PREFIX=$PREFIX']`
- **ported**: `generic.toml`

## bzip2/source.lua

- **ported**: `source.toml`

## c-ares/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/c-ares@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-static', '--disable-shared', '--with-pic', '--disable-tests']`
- **ported**: `generic.toml`

## c-ares/source.lua

- **ported**: `source.toml`

## cairo/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/cairo@source/* .`
- **driven by the meson build system**: `args=['-Dbuildtype=release', '-Ddefault_library=static', '-Dpng=enabled', '-Dzlib=enabled', '-Dfreetype=enabled', '-Dfontconfig=enabled', '-Dxlib=disabled', '-Dxcb=disabled', '-Dxlib-xcb=disabled', '-`
- **ported**: `generic.toml`

## cairo/source.lua

- **ported**: `source.toml`

## capnproto/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/capnproto@source/* .`
- **driven by the autoconf build system**: `make=False, install=False, configure_args=['--enable-static', '--disable-shared', '--without-fibers', '--with-zlib', '--with-openssl']`
- **ported**: `generic.toml`

## capnproto/source.lua

- **ported**: `source.toml`

## catch2/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/catch2@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DCATCH_INSTALL_DOCS=OFF', '-DCATCH_INSTALL_EXTRAS=OFF']`
- **ported**: `generic.toml`

## catch2/source.lua

- **ported**: `source.toml`

## ccache/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/ccache@source/* .`
- **driven by the cmake build system**: `args=['-DENABLE_TESTING=OFF', '-DENABLE_DOCUMENTATION=OFF', '-DREDIS_STORAGE_BACKEND=OFF', '-DHTTP_STORAGE_BACKEND=OFF']`
- **ported**: `generic.toml`

## ccache/source.lua

- **ported**: `source.toml`

## cjson/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/cjson@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DENABLE_CUSTOM_COMPILER_FLAGS=OFF', '-DENABLE_CJSON_TEST=OFF']`
- **ported**: `generic.toml`

## cjson/source.lua

- **ported**: `source.toml`

## cmark/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/cmark@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DBUILD_TESTING=OFF']`
- **ported**: `generic.toml`

## cmark/source.lua

- **ported**: `source.toml`

## cmph/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/cmph@source/* .`
- **driven by the autoconf build system**: `configure_args=['--disable-cxxmph', '--disable-benchmarks', '--disable-check']`
- **ported**: `generic.toml`

## cmph/source.lua

- **ported**: `source.toml`

## coreutils/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/coreutils@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-no-install-program=kill,uptime']`
- **ported**: `generic.toml`

## coreutils/source.lua

- **ported**: `source.toml`

## cppcheck/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/cppcheck@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DDISABLE_DMAKE=ON']`
- **ported**: `generic.toml`

## cppcheck/source.lua

- **ported**: `source.toml`

## cscope/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/cscope@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## cscope/source.lua

- **ported**: `source.toml`

## curl/android.lua

- **FLAGGED $PREFIX meaning dependencies**: `./configure $AUTOCONF_CONFIGURE_FLAGS --disable-shared --enable-static --without-ssl --with-zlib="$PREFIX" --without-libpsl --without-libidn2 --without-nghttp2 --without-nghttp3 --without-libssh2 --di`

## curl/android.toml

- **fixed by hand (zlib is a declared dependency with its own directory)**: `--with-zlib="\$\{RETROLUNAR_PORT_PREFIX\}"`

## curl/android.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/curl@source/* .`
- **driven by the autoconf build system**: `make=False, install=False, configure_args=['--disable-shared', '--enable-static', '--without-ssl', '--with-zlib=$zlib_PREFIX', '--without-libpsl', '--without-libidn2', '--without-nghttp2', '--without-`
- **ported**: `android.toml`

## curl/generic.lua

- **FLAGGED $PREFIX meaning dependencies**: `./configure $AUTOCONF_CONFIGURE_FLAGS --disable-shared --enable-static --with-zlib="$PREFIX" --without-libpsl --without-libidn2 --without-nghttp2 --without-nghttp3 --without-libssh2 --disable-ldap --d`

## curl/generic.toml

- **fixed by hand (zlib is a declared dependency with its own directory)**: `--with-zlib="\$\{RETROLUNAR_PORT_PREFIX\}"`

## curl/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/curl@source/* .`
- **driven by the autoconf build system**: `make=False, install=False, configure_args=['--disable-shared', '--enable-static', '--with-zlib=$zlib_PREFIX', '--without-libpsl', '--without-libidn2', '--without-nghttp2', '--without-nghttp3', '--with`
- **ported**: `generic.toml`

## curl/source.lua

- **ported**: `source.toml`

## dejagnu/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/dejagnu@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## dejagnu/source.lua

- **ported**: `source.toml`

## diffutils/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/diffutils@source/* .`
- **driven by the autoconf build system**: `make=False, install=False`
- **ported**: `generic.toml`

## diffutils/source.lua

- **ported**: `source.toml`

## distcc/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/distcc@source/* .`
- **driven by the autoconf build system**: `configure_args=['--with-included-popt', '--disable-pump-mode']`
- **ported**: `generic.toml`

## distcc/source.lua

- **ported**: `source.toml`

## doctest/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/doctest@source/* .`
- **driven by the cmake build system**: `args=['-DDOCTEST_WITH_TESTS=OFF', '-DDOCTEST_WITH_MAIN_IN_STATIC_LIB=ON']`
- **ported**: `generic.toml`

## doctest/source.lua

- **ported**: `source.toml`

## doxygen/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/doxygen@source/* .`
- **driven by the cmake build system**: `args=['-Dbuild_wizard=OFF', '-Dbuild_doc=OFF']`
- **ported**: `generic.toml`

## doxygen/source.lua

- **ported**: `source.toml`

## dpl/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/dpl@source/* .`
- **driven by the cmake build system**: `args=['-DONEDPL_BACKEND=serial']`
- **ported**: `generic.toml`

## dpl/source.lua

- **ported**: `source.toml`

## draco/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/draco@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DDRACO_TESTS=OFF']`
- **ported**: `generic.toml`

## draco/source.lua

- **ported**: `source.toml`

## e2fsprogs/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `--sysconfdir="$OUT/etc" \`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/e2fsprogs@source/* .`
- **driven by the autoconf build system**: `configure_args=['--sysconfdir=$PREFIX/etc', '--enable-elf-shlibs', '--disable-libblkid', '--disable-libuuid', '--disable-uuidd', '--disable-fsck']`
- **ported**: `generic.toml`

## e2fsprogs/source.lua

- **ported**: `source.toml`

## easylogging-plusplus/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/easylogging-plusplus@source/* .`
- **driven by the cmake build system**: `args=['-Dbuild_static_lib=OFF', '-Dtest=OFF']`
- **ported**: `generic.toml`

## easylogging-plusplus/source.lua

- **ported**: `source.toml`

## elfutils/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/lib/pkgconfig`
- **rewrote $OUT to $PREFIX (staging)**: `cp config/libelf.pc $OUT/lib/pkgconfig/`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/elfutils@source/* .`
- **driven by the autoconf build system**: `make=False, install=False, configure_args=['--disable-debuginfod', '--enable-libdebuginfod=dummy']`
- **ported**: `generic.toml`

## elfutils/source.lua

- **ported**: `source.toml`

## expat/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/expat@source/* .`
- **driven by the cmake build system**: `args=['-DEXPAT_SHARED_LIBS=OFF', '-DEXPAT_BUILD_TOOLS=OFF', '-DEXPAT_BUILD_TESTS=OFF', '-DEXPAT_BUILD_EXAMPLES=OFF', '-DEXPAT_BUILD_DOCS=OFF']`
- **ported**: `generic.toml`

## expat/source.lua

- **ported**: `source.toml`

## expect/generic.lua

- **FLAGGED $PREFIX meaning dependencies**: `--with-tcl="$PREFIX/lib" \`
- **FLAGGED $PREFIX meaning dependencies**: `--with-tclinclude="$PREFIX/include" \`
- **rewrote $OUT to $PREFIX (staging)**: `--mandir="$OUT/share/man"`

## expect/generic.toml

- **fixed by hand (tcl is a declared dependency)**: `--with-tcl="\$\{RETROLUNAR_PORT_PREFIX\}/lib"`
- **fixed by hand (tcl is a declared dependency)**: `--with-tclinclude="\$\{RETROLUNAR_PORT_PREFIX\}/include"`
- **fixed by hand (v1's shared native prefix is the host tcl's own directory in v2)**: `\$NATIVE_PREFIX/bin/tclsh8\.6`
- **fixed by hand (the comment named the v1 prefix)**: `# why it must not point at \$NATIVE_PREFIX\.`

## expect/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/expect@source/* .`
- **driven by the autoconf build system**: `make=False, install=False, configure_args=['--with-tcl=$tcl_PREFIX/lib', '--with-tclinclude=$tcl_PREFIX/include', '--enable-shared', '--disable-rpath', '--mandir=$PREFIX/share/man']`
- **ported**: `generic.toml`

## expect/source.lua

- **ported**: `source.toml`

## ffmpeg/android.lua

- **rewrote $OUT to $OUTPKG (install prefix)**: `./configure --prefix="$OUT" --enable-cross-compile --arch="$ffmpeg_arch" --target-os="$HOST_OS" --cc="$CC" --cxx="$CXX" --ar="$AR" --ranlib="$RANLIB" --strip="$STRIP" --pkg-config-flags="--static" --e`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/ffmpeg@source/* .`
- **driven by the autoconf build system**: `configure_args=['--prefix=$OUTPKG', '--enable-cross-compile', '--arch=$ffmpeg_arch', '--target-os=$HOST_OS', '--cc=$CC', '--cxx=$CXX', '--ar=$AR', '--ranlib=$RANLIB', '--strip=$STRIP', '--pkg-config-f`
- **ported**: `android.toml`

## ffmpeg/generic.lua

- **rewrote $OUT to $OUTPKG (install prefix)**: `./configure --prefix="$OUT" --cc="$CC" --cxx="$CXX" --ar="$AR" --ranlib="$RANLIB" --strip="$STRIP" --pkg-config-flags="--static" --enable-static --disable-shared --disable-doc --disable-programs --dis`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/ffmpeg@source/* .`
- **driven by the autoconf build system**: `configure_args=['--prefix=$OUTPKG', '--cc=$CC', '--cxx=$CXX', '--ar=$AR', '--ranlib=$RANLIB', '--strip=$STRIP', '--pkg-config-flags=--static', '--enable-static', '--disable-shared', '--disable-doc', '`
- **ported**: `generic.toml`

## ffmpeg/source.lua

- **ported**: `source.toml`

## fftw/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/fftw@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-static', '--disable-shared', '--disable-fortran', '--disable-doc']`
- **ported**: `generic.toml`

## fftw/source.lua

- **ported**: `source.toml`

## file/clang-native.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/file@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `clang-native.toml`

## file/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/file@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## file/source.lua

- **ported**: `source.toml`

## findutils/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `./configure $AUTOCONF_CONFIGURE_FLAGS --localstatedir="$OUT/var/lib/locate"`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/findutils@source/* .`
- **driven by the autoconf build system**: `configure_args=['--localstatedir=$PREFIX/var/lib/locate']`
- **ported**: `generic.toml`

## findutils/source.lua

- **ported**: `source.toml`

## flac/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/flac@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-static', '--disable-shared', '--with-pic', '--disable-version-from-git']`
- **ported**: `generic.toml`

## flac/source.lua

- **ported**: `source.toml`

## flatbuffers/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/flatbuffers@source/* .`
- **driven by the cmake build system**: `args=['-DFLATBUFFERS_BUILD_TESTS=OFF', '-DFLATBUFFERS_BUILD_GRPCTEST=OFF', '-DFLATBUFFERS_BUILD_SHAREDLIB=OFF', '-DFLATBUFFERS_INSTALL=ON']`
- **ported**: `generic.toml`

## flatbuffers/source.lua

- **ported**: `source.toml`

## flex/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/flex@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-static', '--disable-shared', '--with-pic', '--disable-bootstrap']`
- **ported**: `generic.toml`

## flex/source.lua

- **ported**: `source.toml`

## flit-core/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/lib/python3.14/site-packages`
- **rewrote $OUT to $PREFIX (staging)**: `cp -r flit_core $OUT/lib/python3.14/site-packages/`
- **rewrote $OUT to $PREFIX (staging)**: `cp LICENSE $OUT/lib/python3.14/site-packages/flit_core/LICENSE`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/flit-core@source/* .`
- **driven by the python build system**: `modules=['flit_core'], licenses=['LICENSE']`
- **ported**: `generic.toml`

## flit-core/source.lua

- **ported**: `source.toml`

## fmt/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/fmt@source/* .`
- **driven by the cmake build system**: `args=['-DFMT_TEST=OFF', '-DFMT_DOC=OFF', '-DFMT_INSTALL=ON', '-DBUILD_SHARED_LIBS=OFF']`
- **ported**: `generic.toml`

## fmt/source.lua

- **ported**: `source.toml`

## fontconfig/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/fontconfig@source/* .`
- **driven by the meson build system**: `args=['-Dbuildtype=release', '-Ddefault_library=static', '-Dxml-backend=expat', '-Dnls=disabled', '-Dtools=disabled', '-Dcache-build=disabled', '-Dtests=disabled', '-Dtests-external-fonts=disabled', '`
- **ported**: `generic.toml`

## fontconfig/source.lua

- **ported**: `source.toml`

## freetype/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/freetype@source/* .`
- **driven by the meson build system**: `args=['-Ddefault_library=static', '-Dzlib=system', '-Dpng=enabled', '-Dbrotli=disabled', '-Dbzip2=disabled', '-Dharfbuzz=disabled', '-Dtests=disabled']`
- **ported**: `generic.toml`

## freetype/source.lua

- **ported**: `source.toml`

## fribidi/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/fribidi@source/* .`
- **driven by the meson build system**: `args=['-Dbuildtype=release', '-Ddefault_library=static', '-Dtests=false', '-Ddocs=false', '-Dbin=false']`
- **ported**: `generic.toml`

## fribidi/source.lua

- **ported**: `source.toml`

## gawk/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/gawk@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## gawk/source.lua

- **ported**: `source.toml`

## gdbm/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/gdbm@source/* .`
- **driven by the autoconf build system**: `configure_args=['--disable-static', '--enable-libgdbm-compat']`
- **ported**: `generic.toml`

## gdbm/source.lua

- **ported**: `source.toml`

## gettext/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `chmod 0755 $OUT/lib/preloadable_libintl.so`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/gettext@source/* .`
- **driven by the autoconf build system**: `configure_args=['--disable-static']`
- **ported**: `generic.toml`

## gettext/source.lua

- **ported**: `source.toml`

## giflib/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `make -j"$CORES" CC="$CC" CFLAGS="$CFLAGS" LDFLAGS="$LDFLAGS" PREFIX="$OUT"`
- **rewrote $OUT to $PREFIX (staging)**: `make install-lib install-include PREFIX="$OUT"`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/giflib@source/* .`
- **driven by the make build system**: `make=False, install=False, make_args=['PREFIX=$PREFIX'], targets=['install-lib', 'install-include']`
- **ported**: `generic.toml`

## giflib/source.lua

- **ported**: `source.toml`

## glad/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p obj $OUT/lib $OUT/include`
- **rewrote $OUT to $PREFIX (staging)**: `$AR rcs $OUT/lib/libglad.a obj/gl.o obj/gles2.o obj/egl.o`
- **rewrote $OUT to $PREFIX (staging)**: `$RANLIB $OUT/lib/libglad.a`
- **rewrote $OUT to $PREFIX (staging)**: `cp -r glad-out/include/. $OUT/include/`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/lib/pkgconfig`
- **rewrote $OUT to $PREFIX (staging)**: `cat > $OUT/lib/pkgconfig/glad.pc <<EOF`
- **FLAGGED $PREFIX meaning dependencies**: `prefix=$PREFIX`

## glad/generic.toml

- **fixed by hand (an install prefix: the final path, DESTDIR redirects the write)**: `prefix=\$\{RETROLUNAR_PORT_PREFIX\}`

## glad/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/glad@source/* .`
- **left as a shell body (a compilation of its own, not a build system)**: `generic.lua`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p obj $OUT/lib $OUT/include`
- **rewrote $OUT to $PREFIX (staging)**: `$AR rcs $OUT/lib/libglad.a obj/gl.o obj/gles2.o obj/egl.o`
- **rewrote $OUT to $PREFIX (staging)**: `$RANLIB $OUT/lib/libglad.a`
- **rewrote $OUT to $PREFIX (staging)**: `cp -r glad-out/include/. $OUT/include/`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/lib/pkgconfig`
- **rewrote $OUT to $PREFIX (staging)**: `cat > $OUT/lib/pkgconfig/glad.pc <<EOF`
- **FLAGGED $PREFIX meaning dependencies**: `prefix=$PREFIX`

## glad/generic.toml

- **fixed by hand (an install prefix: the final path, DESTDIR redirects the write)**: `prefix=\$\{RETROLUNAR_PORT_PREFIX\}`

## glad/generic.lua

- **ported**: `generic.toml`

## glad/source.lua

- **ported**: `source.toml`

## glew/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `make -j"$CORES" glew.lib.static CC="$CC" AR="$AR" RANLIB="$RANLIB" STRIP= GLEW_DEST="$OUT" GLEW_PREFIX="$OUT" LIBDIR="$OUT/lib" LDFLAGS.GL= GLEW_NO_GLU=-DGLEW_NO_GLU`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/include/GL $OUT/lib/pkgconfig`
- **rewrote $OUT to $PREFIX (staging)**: `cp include/GL/glew.h include/GL/glxew.h include/GL/wglew.h include/GL/eglew.h $OUT/include/GL/`
- **rewrote $OUT to $PREFIX (staging)**: `cp lib/libGLEW.a $OUT/lib/`
- **rewrote $OUT to $PREFIX (staging)**: `cp glew.pc $OUT/lib/pkgconfig/`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/glew@source/* .`
- **driven by the make build system**: `make=False, install=False, targets=['glew.lib.static'], make_args=['STRIP=', 'GLEW_DEST=$PREFIX', 'GLEW_PREFIX=$PREFIX', 'LIBDIR=$PREFIX/lib', 'LDFLAGS.GL=', 'GLEW_NO_GLU=-DGLEW_NO_GLU']`
- **ported**: `generic.toml`

## glew/source.lua

- **ported**: `source.toml`

## glfw/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/glfw@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DGLFW_BUILD_X11=OFF', '-DGLFW_BUILD_WAYLAND=OFF', '-DGLFW_BUILD_EXAMPLES=OFF', '-DGLFW_BUILD_TESTS=OFF', '-DGLFW_BUILD_DOCS=OFF']`
- **ported**: `generic.toml`

## glfw/source.lua

- **ported**: `source.toml`

## glm/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/glm@source/* .`
- **driven by the cmake build system**: `args=['-DGLM_BUILD_LIBRARY=OFF', '-DGLM_BUILD_TESTS=OFF', '-DGLM_BUILD_INSTALL=ON']`
- **ported**: `generic.toml`

## glm/source.lua

- **ported**: `source.toml`

## glog/android.lua

- **rewrote $OUT to $PREFIX (staging)**: `awk '{ if ($0 ~ /^Cflags:/) print $0 " -DGLOG_USE_GLOG_EXPORT"; else print }' "$OUT/lib/pkgconfig/libglog.pc" > "$WORK/libglog.pc"`
- **rewrote $OUT to $PREFIX (staging)**: `cp "$WORK/libglog.pc" "$OUT/lib/pkgconfig/libglog.pc"`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/glog@source/* .`
- **driven by the cmake build system**: `args=['-DANDROID=ON', '-DBUILD_SHARED_LIBS=OFF', '-DBUILD_TESTING=OFF', '-DWITH_GFLAGS=OFF', '-DWITH_GTEST=OFF', '-DWITH_GMOCK=OFF', '-DWITH_PKGCONFIG=ON', '-DWITH_UNWIND=none']`
- **ported**: `android.toml`

## glog/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `awk '{ if ($0 ~ /^Cflags:/) print $0 " -DGLOG_USE_GLOG_EXPORT"; else print }' "$OUT/lib/pkgconfig/libglog.pc" > "$WORK/libglog.pc"`
- **rewrote $OUT to $PREFIX (staging)**: `cp "$WORK/libglog.pc" "$OUT/lib/pkgconfig/libglog.pc"`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/glog@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DBUILD_TESTING=OFF', '-DWITH_GFLAGS=OFF', '-DWITH_GTEST=OFF', '-DWITH_GMOCK=OFF', '-DWITH_PKGCONFIG=ON', '-DWITH_UNWIND=none']`
- **ported**: `generic.toml`

## glog/source.lua

- **ported**: `source.toml`

## gmp/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/gmp@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-cxx', '--disable-static']`
- **ported**: `generic.toml`

## gmp/source.lua

- **ported**: `source.toml`

## googletest/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/googletest@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-Dgtest_build_tests=OFF', '-Dgmock_build_tests=OFF']`
- **ported**: `generic.toml`

## googletest/source.lua

- **ported**: `source.toml`

## gperf/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/gperf@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## gperf/source.lua

- **ported**: `source.toml`

## graphite2/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/graphite2@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DBUILD_TESTING=OFF']`
- **ported**: `generic.toml`

## graphite2/source.lua

- **ported**: `source.toml`

## grep/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/grep@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## grep/source.lua

- **ported**: `source.toml`

## groff/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/groff@source/* .`
- **driven by the make build system**: `no arguments`
- **ported**: `generic.toml`

## groff/source.lua

- **ported**: `source.toml`

## grub/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/grub@source/* .`
- **driven by the autoconf build system**: `make=False, install=False, configure_args=['--sysconfdir=/etc', '--disable-efiemu', '--disable-werror']`
- **ported**: `generic.toml`

## grub/source.lua

- **ported**: `source.toml`

## gumbo/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/gumbo@source/* .`
- **driven by the meson build system**: `args=['-Dbuildtype=release', '-Ddefault_library=static', '-Dtests=false', '-Dexamples=false', '-Dfuzz=false', '-Dpython=false']`
- **ported**: `generic.toml`

## gumbo/source.lua

- **ported**: `source.toml`

## gzip/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/gzip@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## gzip/source.lua

- **ported**: `source.toml`

## harfbuzz/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/harfbuzz@source/* .`
- **driven by the meson build system**: `args=['-Dbuildtype=release', '-Ddefault_library=static', '-Dtests=disabled', '-Ddocs=disabled', '-Dutilities=disabled', '-Dintrospection=disabled', '-Dfreetype=enabled', '-Dglib=disabled', '-Dgobject=`
- **ported**: `generic.toml`

## harfbuzz/source.lua

- **ported**: `source.toml`

## heaptrack/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/heaptrack@source/* .`
- **driven by the cmake build system**: `no arguments`
- **ported**: `generic.toml`

## heaptrack/source.lua

- **ported**: `source.toml`

## hello/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/bin`
- **rewrote $OUT to $PREFIX (staging)**: `$CC $CFLAGS main.c -o $OUT/bin/hello`
- **left as a shell body (a compilation of its own, not a build system)**: `generic.lua`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/bin`
- **rewrote $OUT to $PREFIX (staging)**: `$CC $CFLAGS main.c -o $OUT/bin/hello`
- **ported**: `generic.toml`

## main.c

- **copied unchanged**: `main.c`

## hello/source.lua

- **ported**: `source.toml`

## highway/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/highway@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DHWY_ENABLE_CONTRIB=ON', '-DHWY_ENABLE_INSTALL=ON', '-DHWY_ENABLE_TESTS=OFF', '-DHWY_ENABLE_EXAMPLES=OFF']`
- **ported**: `generic.toml`

## highway/source.lua

- **ported**: `source.toml`

## hwloc/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/hwloc@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-static', '--disable-shared', '--disable-picky']`
- **ported**: `generic.toml`

## hwloc/source.lua

- **ported**: `source.toml`

## i2pd/android.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/etc/i2pd/tunnels.conf.d`
- **rewrote $OUT to $PREFIX (staging)**: `cp contrib/i2pd.conf contrib/subscriptions.txt contrib/tunnels.conf $OUT/etc/i2pd/`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/share/doc/i2pd`
- **rewrote $OUT to $PREFIX (staging)**: `cp ChangeLog LICENSE README.md contrib/i2pd.conf contrib/subscriptions.txt contrib/tunnels.conf $OUT/share/doc/i2pd/`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/share/i2pd`
- **rewrote $OUT to $PREFIX (staging)**: `cp -r contrib/certificates $OUT/share/i2pd/`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/share/man/man1`
- **rewrote $OUT to $PREFIX (staging)**: `cp debian/i2pd.1 $OUT/share/man/man1/`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/include/i2pd`
- **rewrote $OUT to $PREFIX (staging)**: `cp i18n/*.h libi2pd/*.h libi2pd_client/*.h $OUT/include/i2pd/`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/var/lib/i2pd/tunnels.d`
- **rewrote $OUT to $PREFIX (staging)**: `cp -r contrib/certificates $OUT/var/lib/i2pd/`
- **rewrote $OUT to $PREFIX (staging)**: `cp contrib/i2pd.conf contrib/subscriptions.txt contrib/tunnels.conf $OUT/var/lib/i2pd/`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/i2pd@source/* .`
- **driven by the cmake build system**: `args=['-DWITH_UPNP=OFF', '-DWITH_GIT_VERSION=OFF', '-DBUILD_TESTING=OFF'], source_dir=build`
- **ported**: `android.toml`

## i2pd/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/etc/i2pd/tunnels.conf.d`
- **rewrote $OUT to $PREFIX (staging)**: `cp contrib/i2pd.conf contrib/subscriptions.txt contrib/tunnels.conf $OUT/etc/i2pd/`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/share/doc/i2pd`
- **rewrote $OUT to $PREFIX (staging)**: `cp ChangeLog LICENSE README.md contrib/i2pd.conf contrib/subscriptions.txt contrib/tunnels.conf $OUT/share/doc/i2pd/`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/share/i2pd`
- **rewrote $OUT to $PREFIX (staging)**: `cp -r contrib/certificates $OUT/share/i2pd/`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/share/man/man1`
- **rewrote $OUT to $PREFIX (staging)**: `cp debian/i2pd.1 $OUT/share/man/man1/`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/include/i2pd`
- **rewrote $OUT to $PREFIX (staging)**: `cp i18n/*.h libi2pd/*.h libi2pd_client/*.h $OUT/include/i2pd/`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/var/lib/i2pd/tunnels.d`
- **rewrote $OUT to $PREFIX (staging)**: `cp -r contrib/certificates $OUT/var/lib/i2pd/`
- **rewrote $OUT to $PREFIX (staging)**: `cp contrib/i2pd.conf contrib/subscriptions.txt contrib/tunnels.conf $OUT/var/lib/i2pd/`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/i2pd@source/* .`
- **driven by the cmake build system**: `args=['-DWITH_UPNP=OFF', '-DWITH_GIT_VERSION=OFF', '-DBUILD_TESTING=OFF'], source_dir=build`
- **ported**: `generic.toml`

## i2pd/source.lua

- **ported**: `source.toml`

## iana-etc/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/etc`
- **rewrote $OUT to $PREFIX (staging)**: `cp $NESTDIR/source/iana-etc/services $NESTDIR/source/iana-etc/protocols $OUT/etc/`
- **left as a shell body (installing files is the whole recipe)**: `generic.lua`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/etc`
- **rewrote $OUT to $PREFIX (staging)**: `cp $NESTDIR/source/iana-etc/services $NESTDIR/source/iana-etc/protocols $OUT/etc/`
- **ported**: `generic.toml`

## iana-etc/source.lua

- **ported**: `source.toml`

## imgui/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p obj $OUT/lib $OUT/include $OUT/lib/pkgconfig`
- **rewrote $OUT to $PREFIX (staging)**: `$AR rcs $OUT/lib/libimgui.a obj/*.o`
- **rewrote $OUT to $PREFIX (staging)**: `$RANLIB $OUT/lib/libimgui.a`
- **rewrote $OUT to $PREFIX (staging)**: `cp imgui.h imgui_internal.h imconfig.h imstb_rectpack.h imstb_textedit.h imstb_truetype.h LICENSE.txt $OUT/include/`
- **rewrote $OUT to $PREFIX (staging)**: `cat > $OUT/lib/pkgconfig/imgui.pc <<EOF`
- **FLAGGED $PREFIX meaning dependencies**: `prefix=$PREFIX`

## imgui/generic.toml

- **fixed by hand (an install prefix: the final path, DESTDIR redirects the write)**: `prefix=\$\{RETROLUNAR_PORT_PREFIX\}`

## imgui/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/imgui@source/* .`
- **left as a shell body (a compilation of its own, not a build system)**: `generic.lua`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p obj $OUT/lib $OUT/include $OUT/lib/pkgconfig`
- **rewrote $OUT to $PREFIX (staging)**: `$AR rcs $OUT/lib/libimgui.a obj/*.o`
- **rewrote $OUT to $PREFIX (staging)**: `$RANLIB $OUT/lib/libimgui.a`
- **rewrote $OUT to $PREFIX (staging)**: `cp imgui.h imgui_internal.h imconfig.h imstb_rectpack.h imstb_textedit.h imstb_truetype.h LICENSE.txt $OUT/include/`
- **rewrote $OUT to $PREFIX (staging)**: `cat > $OUT/lib/pkgconfig/imgui.pc <<EOF`
- **FLAGGED $PREFIX meaning dependencies**: `prefix=$PREFIX`

## imgui/generic.toml

- **fixed by hand (an install prefix: the final path, DESTDIR redirects the write)**: `prefix=\$\{RETROLUNAR_PORT_PREFIX\}`

## imgui/generic.lua

- **ported**: `generic.toml`

## imgui/source.lua

- **ported**: `source.toml`

## inetutils/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `ln -s ../sbin/ifconfig $OUT/bin/ifconfig`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/inetutils@source/* .`
- **driven by the autoconf build system**: `make=False, install=False, configure_args=['--bindir=/usr/bin', '--localstatedir=/var', '--disable-logger', '--disable-whois', '--disable-rcp', '--disable-rexec', '--disable-rlogin', '--disable-rsh', `
- **ported**: `generic.toml`

## inetutils/source.lua

- **ported**: `source.toml`

## intltool/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/intltool@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## intltool/source.lua

- **ported**: `source.toml`

## isa-l/generic.lua

- **rewrote $OUT to $OUTPKG (install prefix)**: `make -j"$CORES" -f Makefile.unx host_cpu="$HOST_ARCH" prefix="$OUT" install`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/isa-l@source/* .`
- **driven by the make build system**: `make=False, install=False, targets=['Makefile.unx'], make_args=['-f', 'host_cpu=$HOST_ARCH', 'prefix=$OUTPKG']`
- **ported**: `generic.toml`

## isa-l/source.lua

- **ported**: `source.toml`

## jansson/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/jansson@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-static', '--disable-shared', '--with-pic']`
- **ported**: `generic.toml`

## jansson/source.lua

- **ported**: `source.toml`

## jasper/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/jasper@source/* .`
- **driven by the cmake build system**: `args=['-DJAS_ENABLE_SHARED=OFF', '-DJAS_ENABLE_LIBJPEG=ON', '-DJAS_ENABLE_LIBHEIF=OFF', '-DJAS_ENABLE_OPENGL=OFF', '-DJAS_ENABLE_PROGRAMS=OFF', '-DJAS_ENABLE_DOC=OFF', '-DJAS_ENABLE_LATEX=OFF']`
- **ported**: `generic.toml`

## jasper/source.lua

- **ported**: `source.toml`

## jinja2/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/lib/python3.14/site-packages`
- **rewrote $OUT to $PREFIX (staging)**: `cp -r src/jinja2 $OUT/lib/python3.14/site-packages/`
- **rewrote $OUT to $PREFIX (staging)**: `cp LICENSE.txt $OUT/lib/python3.14/site-packages/jinja2/LICENSE.txt`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/jinja2@source/* .`
- **driven by the python build system**: `modules=['src/jinja2'], licenses=['LICENSE.txt']`
- **ported**: `generic.toml`

## jinja2/source.lua

- **ported**: `source.toml`

## json-c/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/json-c@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DBUILD_STATIC_LIBS=ON', '-DBUILD_APPS=OFF', '-DBUILD_TESTING=OFF', '-DDISABLE_WERROR=ON']`
- **ported**: `generic.toml`

## json-c/source.lua

- **ported**: `source.toml`

## kbd/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/kbd@source/* .`
- **driven by the autoconf build system**: `configure_args=['--disable-vlock']`
- **ported**: `generic.toml`

## kbd/source.lua

- **ported**: `source.toml`

## kissfft/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/kissfft@source/* .`
- **driven by the cmake build system**: `args=['-DKISSFFT_STATIC=ON', '-DKISSFFT_TEST=OFF', '-DKISSFFT_TOOLS=OFF', '-DKISSFFT_DATATYPE=double']`
- **ported**: `generic.toml`

## kissfft/source.lua

- **ported**: `source.toml`

## kmod/android.lua

- **driven by the meson build system**: `args=['-Dbashcompletiondir=', '-Dfishcompletiondir=', '-Dmanpages=false', '-Dzlib=disabled', '-Dxz=enabled', '-Dzstd=disabled']`
- **ported**: `android.toml`

## kmod/generic.lua

- **driven by the meson build system**: `args=['-Dbashcompletiondir=', '-Dfishcompletiondir=', '-Dmanpages=false', '-Dxz=enabled', '-Dzstd=disabled']`
- **ported**: `generic.toml`

## kmod/source.lua

- **ported**: `source.toml`

## lame/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/lame@source/* .`
- **driven by the autoconf build system**: `make=False, install=False, configure_args=['--disable-shared', '--enable-static', '--disable-frontend', '--disable-gtktest', '--disable-nasm']`
- **ported**: `generic.toml`

## lame/source.lua

- **ported**: `source.toml`

## lapack/generic.lua

- **left as a shell body (the recipe reports it cannot be built here)**: `generic.lua`
- **ported**: `generic.toml`

## lapack/source.lua

- **ported**: `source.toml`

## lcms2/generic.lua

- **FLAGGED $PREFIX meaning dependencies**: `./configure $AUTOCONF_CONFIGURE_FLAGS --enable-static --disable-shared --with-pic --with-jpeg="$PREFIX" --with-tiff="$PREFIX" --without-python --disable-utils`

## lcms2/generic.toml

- **fixed by hand (libjpeg-turbo is a declared dependency)**: `--with-jpeg="\$\{RETROLUNAR_PORT_PREFIX\}"`
- **fixed by hand (libtiff is a declared dependency)**: `--with-tiff="\$\{RETROLUNAR_PORT_PREFIX\}"`

## lcms2/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/lcms2@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-static', '--disable-shared', '--with-pic', '--with-jpeg=$libjpeg_turbo_PREFIX', '--with-tiff=$libtiff_PREFIX', '--without-python', '--disable-utils']`
- **ported**: `generic.toml`

## lcms2/source.lua

- **ported**: `source.toml`

## less/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/less@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## less/source.lua

- **ported**: `source.toml`

## lfs-bootscripts/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/etc`
- **rewrote $OUT to $PREFIX (staging)**: `cp -r $NESTDIR/source/lfs-bootscripts/* $OUT/etc/`
- **left as a shell body (installing files is the whole recipe)**: `generic.lua`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/etc`
- **rewrote $OUT to $PREFIX (staging)**: `cp -r $NESTDIR/source/lfs-bootscripts/* $OUT/etc/`
- **ported**: `generic.toml`

## lfs-bootscripts/source.lua

- **ported**: `source.toml`

## libarchive/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libarchive@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-static', '--disable-shared', '--with-pic', '--without-xml2', '--without-expat', '--disable-bsdtar', '--disable-bsdcp', '--disable-bsdcat', '--disable-tests']`
- **ported**: `generic.toml`

## libarchive/source.lua

- **ported**: `source.toml`

## libcap/generic.lua

- **rewrote $OUT to $OUTPKG (install prefix)**: `lib=lib prefix="$OUT" SHARED=no PTHREADS=yes USE_GPERF=no \`
- **rewrote $OUT to $OUTPKG (install prefix)**: `lib=lib prefix="$OUT" SHARED=no PTHREADS=yes USE_GPERF=no \`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libcap@source/* .`
- **driven by the make build system**: `make=False, install=False, targets=['libcap'], make_args=['-C', 'BUILD_CC=cc', 'lib=lib', 'prefix=$OUTPKG', 'SHARED=no', 'PTHREADS=yes', 'USE_GPERF=no', 'PAM_CAP=no', 'GOLANG=no']`
- **ported**: `generic.toml`

## libcap/source.lua

- **ported**: `source.toml`

## libcbor/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libcbor@source/* .`
- **driven by the cmake build system**: `args=['-DWITH_EXAMPLES=OFF', '-DSANITIZE=OFF', '-DCMAKE_C_STANDARD=99']`
- **ported**: `generic.toml`

## libcbor/source.lua

- **ported**: `source.toml`

## libconfig/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libconfig@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DBUILD_EXAMPLES=OFF', '-DBUILD_TESTS=OFF']`
- **ported**: `generic.toml`

## libconfig/source.lua

- **ported**: `source.toml`

## libevent/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libevent@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-static', '--disable-shared', '--with-pic', '--enable-openssl', '--disable-samples', '--disable-libevent-regress', '--disable-benchmark']`
- **ported**: `generic.toml`

## libevent/source.lua

- **ported**: `source.toml`

## libffi/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libffi@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## libffi/source.lua

- **ported**: `source.toml`

## libgit2/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libgit2@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DBUILD_TESTS=OFF', '-DBUILD_CLI=OFF', '-DBUILD_EXAMPLES=OFF', '-DBUILD_FUZZERS=OFF', '-DUSE_SSH=OFF', '-DUSE_HTTPS=OpenSSL', '-DUSE_BUNDLED_ZLIB=OFF', '-DREGEX_BACKE`
- **ported**: `generic.toml`

## libgit2/source.lua

- **ported**: `source.toml`

## libiconv/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libiconv@source/* .`
- **driven by the autoconf build system**: `configure_args=['--disable-shared', '--enable-static', '--disable-nls']`
- **ported**: `generic.toml`

## libiconv/source.lua

- **ported**: `source.toml`

## libjpeg-turbo/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libjpeg-turbo@source/* .`
- **driven by the cmake build system**: `args=['-DENABLE_SHARED=OFF', '-DENABLE_STATIC=ON', '-DWITH_JPEG8=ON']`
- **ported**: `generic.toml`

## libjpeg-turbo/source.lua

- **ported**: `source.toml`

## libmysofa/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libmysofa@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DBUILD_STATIC_LIBS=ON', '-DBUILD_TESTS=OFF']`
- **ported**: `generic.toml`

## libmysofa/source.lua

- **ported**: `source.toml`

## libnl-3/android.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libnl-3@source/* .`
- **driven by the autoconf build system**: `make=False, install=False, configure_args=['--enable-static', '--disable-shared', '--with-pic', '--enable-cli=no', '--disable-pthreads']`
- **ported**: `android.toml`

## libnl-3/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libnl-3@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-static', '--disable-shared', '--with-pic', '--enable-cli=no']`
- **ported**: `generic.toml`

## libnl-3/source.lua

- **ported**: `source.toml`

## libnuma/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libnuma@source/* .`
- **driven by the autoconf build system**: `make=False, install=False, configure_args=['--enable-static', '--disable-shared', '--with-pic']`
- **ported**: `generic.toml`

## libnuma/source.lua

- **ported**: `source.toml`

## libogg/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libogg@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-static', '--disable-shared', '--with-pic', '--disable-oggtest', '--disable-vorbistest']`
- **ported**: `generic.toml`

## libogg/source.lua

- **ported**: `source.toml`

## libpipeline/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libpipeline@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## libpipeline/source.lua

- **ported**: `source.toml`

## libpng/generic.lua

- **FLAGGED $PREFIX meaning dependencies**: `for _f in "$PREFIX/lib"/libzlib.*; do`
- **FLAGGED $PREFIX meaning dependencies**: `[ -f "$PREFIX/lib/libz$_ext" ] || ln -s "libzlib$_ext" "$PREFIX/lib/libz$_ext"`
- **FLAGGED $PREFIX meaning dependencies**: `./configure $AUTOCONF_CONFIGURE_FLAGS --with-zlib-prefix="$PREFIX"`

## libpng/generic.toml

- **fixed by hand (the mingw libz alias moved into zlib's own recipe, where the library is)**: `for _f in "\$\{RETROLUNAR_PORT_PREFIX\}/lib"/libzlib\.\*; do\n[^\n]*\n[^\n]*\n[^\n]*\ndone\n`
- **fixed by hand (the comment pointed at code that is a per-system recipe now)**: `# mingw zlib installs as libzlib \(not libz\), but configure\'s\n# zlib probe hardcodes -lz \(LIBS env can\'t override it: the\n# probe prepends its own -lz, and a missing -l is a hard error\)\.\n# Al`
- **fixed by hand (the closure's -I and -L flags already point at zlib's directory)**: `--with-zlib-prefix="\$\{RETROLUNAR_PORT_PREFIX\}"`

## libpng/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libpng@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## libpng/source.lua

- **ported**: `source.toml`

## libseccomp/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libseccomp@source/* .`
- **driven by the autoconf build system**: `make=False, install=False, configure_args=['--enable-static', '--disable-shared']`
- **ported**: `generic.toml`

## libseccomp/source.lua

- **ported**: `source.toml`

## libsndfile/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libsndfile@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-static', '--disable-shared', '--disable-mpeg', '--disable-alsa', '--disable-sqlite', '--disable-full-suite']`
- **ported**: `generic.toml`

## libsndfile/source.lua

- **ported**: `source.toml`

## libssh2/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libssh2@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-static', '--disable-shared', '--with-pic', '--with-crypto=openssl', '--with-libz', '--disable-examples-build', '--disable-docker-tests', '--disable-sshd-tests']`
- **ported**: `generic.toml`

## libssh2/source.lua

- **ported**: `source.toml`

## libtiff/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libtiff@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-Dtiff-tools=OFF', '-Dtiff-tests=OFF', '-Dtiff-contrib=OFF', '-Dtiff-docs=OFF', '-Dwebp=OFF', '-Dlerc=OFF', '-Dzstd=OFF', '-Dlibdeflate=OFF', '-Dlzma=ON', '-Djpeg=ON'`
- **ported**: `generic.toml`

## libtiff/source.lua

- **ported**: `source.toml`

## libtool/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libtool@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## libtool/source.lua

- **ported**: `source.toml`

## libunwind/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libunwind@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-static', '--disable-shared', '--with-pic', '--disable-tests', '--disable-documentation']`
- **ported**: `generic.toml`

## libunwind/source.lua

- **ported**: `source.toml`

## libuv/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libuv@source/* .`
- **driven by the cmake build system**: `args=['-DLIBUV_BUILD_SHARED=OFF', '-DLIBUV_BUILD_TESTS=OFF', '-DLIBUV_BUILD_BENCH=OFF', '-DLIBUV_ENABLE_DOCS=OFF']`
- **ported**: `generic.toml`

## libuv/source.lua

- **ported**: `source.toml`

## libvorbis/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libvorbis@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-static', '--disable-shared', '--with-pic', '--disable-docs', '--disable-examples']`
- **ported**: `generic.toml`

## libvorbis/source.lua

- **ported**: `source.toml`

## libvpx/android.lua

- **rewrote $OUT to $OUTPKG (install prefix)**: `./configure --prefix="$OUT" --target="$vpx_arch-$HOST_OS-gcc" \`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libvpx@source/* .`
- **driven by the autoconf build system**: `configure_args=['--prefix=$OUTPKG', '--target=$vpx_arch-$HOST_OS-gcc', '--disable-examples', '--disable-docs', '--disable-unit-tests', '--disable-tools', '--enable-pic', '--enable-static', '--disable-`
- **ported**: `android.toml`

## libvpx/generic.lua

- **rewrote $OUT to $OUTPKG (install prefix)**: `./configure --prefix="$OUT" \`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libvpx@source/* .`
- **driven by the autoconf build system**: `configure_args=['--prefix=$OUTPKG', '--disable-examples', '--disable-docs', '--disable-unit-tests', '--disable-tools', '--enable-pic', '--enable-static', '--disable-shared']`
- **ported**: `generic.toml`

## libvpx/source.lua

- **ported**: `source.toml`

## libwebp/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libwebp@source/* .`
- **driven by the cmake build system**: `args=['-DWEBP_BUILD_ANIM_UTILS=OFF', '-DWEBP_BUILD_CWEBP=OFF', '-DWEBP_BUILD_DWEBP=OFF', '-DWEBP_BUILD_GIF2WEBP=OFF', '-DWEBP_BUILD_IMG2WEBP=OFF', '-DWEBP_BUILD_VWEBP=OFF', '-DWEBP_BUILD_WEBPINFO=OFF'`
- **ported**: `generic.toml`

## libwebp/source.lua

- **ported**: `source.toml`

## libxcrypt/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libxcrypt@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-hashes=strong,glibc', '--enable-obsolete-api=glibc']`
- **ported**: `generic.toml`

## libxcrypt/source.lua

- **ported**: `source.toml`

## libxml2/android.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libxml2@source/* .`
- **driven by the autoconf build system**: `configure_args=['--without-python', '--without-docs', '$_iconv_flags']`
- **ported**: `android.toml`

## libxml2/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libxml2@source/* .`
- **driven by the autoconf build system**: `configure_args=['--without-python', '--without-docs']`
- **ported**: `generic.toml`

## libxml2/source.lua

- **ported**: `source.toml`

## libxml2/x86_64-mingw.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libxml2@source/* .`
- **driven by the autoconf build system**: `configure_args=['--without-python', '--without-docs', '--without-iconv']`
- **ported**: `mingw64.toml`

## libxslt/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libxslt@source/* .`
- **driven by the autoconf build system**: `configure_args=['--without-python', '--without-debugger']`
- **ported**: `generic.toml`

## libxslt/source.lua

- **ported**: `source.toml`

## libyaml/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/libyaml@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-static', '--disable-shared', '--with-pic', '--disable-python-bindings']`
- **ported**: `generic.toml`

## libyaml/source.lua

- **ported**: `source.toml`

## lrzip/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/lrzip@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## lrzip/source.lua

- **ported**: `source.toml`

## ltrace/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/ltrace@source/* .`
- **driven by the autoconf build system**: `configure_args=['--disable-libunwind']`
- **ported**: `generic.toml`

## ltrace/source.lua

- **ported**: `source.toml`

## lua/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/include $OUT/lib $OUT/lib/pkgconfig`
- **rewrote $OUT to $PREFIX (staging)**: `cp src/lua.h src/luaconf.h src/lualib.h src/lauxlib.h src/lua.hpp $OUT/include/`
- **rewrote $OUT to $PREFIX (staging)**: `cp liblua.a $OUT/lib/`
- **rewrote $OUT to $PREFIX (staging)**: `cat > $OUT/lib/pkgconfig/lua.pc <<EOF`
- **FLAGGED $PREFIX meaning dependencies**: `prefix=$PREFIX`

## lua/generic.toml

- **fixed by hand (an install prefix: the final path, DESTDIR redirects the write)**: `prefix=\$\{RETROLUNAR_PORT_PREFIX\}`

## lua/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/lua@source/* .`
- **left as a shell body (a compilation of its own, not a build system)**: `generic.lua`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/include $OUT/lib $OUT/lib/pkgconfig`
- **rewrote $OUT to $PREFIX (staging)**: `cp src/lua.h src/luaconf.h src/lualib.h src/lauxlib.h src/lua.hpp $OUT/include/`
- **rewrote $OUT to $PREFIX (staging)**: `cp liblua.a $OUT/lib/`
- **rewrote $OUT to $PREFIX (staging)**: `cat > $OUT/lib/pkgconfig/lua.pc <<EOF`
- **FLAGGED $PREFIX meaning dependencies**: `prefix=$PREFIX`

## lua/generic.toml

- **fixed by hand (an install prefix: the final path, DESTDIR redirects the write)**: `prefix=\$\{RETROLUNAR_PORT_PREFIX\}`

## lua/generic.lua

- **ported**: `generic.toml`

## lua/source.lua

- **ported**: `source.toml`

## lz4/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `make -C lib PREFIX="$OUT" BUILD_SHARED=no BUILD_STATIC=yes`
- **rewrote $OUT to $PREFIX (staging)**: `make -C lib PREFIX="$OUT" BUILD_SHARED=no BUILD_STATIC=yes install`
- **rewrote $OUT to $PREFIX (staging)**: `make -C programs PREFIX="$OUT"`
- **rewrote $OUT to $PREFIX (staging)**: `make -C programs PREFIX="$OUT" install`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/lz4@source/* .`
- **driven by the make build system**: `make=False, install=False, targets=['programs'], make_args=['-C', 'PREFIX=$PREFIX']`
- **ported**: `generic.toml`

## lz4/source.lua

- **ported**: `source.toml`

## lzop/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/lzop@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## lzop/source.lua

- **ported**: `source.toml`

## m4/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/m4@source/* .`
- **driven by the autoconf build system**: `make=False, install=False`
- **ported**: `generic.toml`

## m4/source.lua

- **ported**: `source.toml`

## make/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/make@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## make/source.lua

- **ported**: `source.toml`

## man-db/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/man-db@source/* .`
- **driven by the autoconf build system**: `configure_args=['--disable-setuid', '--enable-cache-owner=bin', '--with-browser=', '--with-vgrind=', '--with-grap=', '--with-systemdtmpfilesdir=', '--with-systemdsystemunitdir=']`
- **ported**: `generic.toml`

## man-db/source.lua

- **ported**: `source.toml`

## man-pages/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/share/man`
- **rewrote $OUT to $PREFIX (staging)**: `cp -r "$_s" "$OUT/share/man/"`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/man-pages@source/* .`
- **left as a shell body (installing files is the whole recipe)**: `generic.lua`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/share/man`
- **rewrote $OUT to $PREFIX (staging)**: `cp -r "$_s" "$OUT/share/man/"`
- **ported**: `generic.toml`

## man-pages/source.lua

- **ported**: `source.toml`

## markupsafe/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/lib/python3.14/site-packages`
- **rewrote $OUT to $PREFIX (staging)**: `cp -r src/markupsafe $OUT/lib/python3.14/site-packages/`
- **rewrote $OUT to $PREFIX (staging)**: `cp LICENSE.txt $OUT/lib/python3.14/site-packages/markupsafe/LICENSE.txt`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/markupsafe@source/* .`
- **driven by the python build system**: `modules=['src/markupsafe'], licenses=['LICENSE.txt']`
- **ported**: `generic.toml`

## markupsafe/source.lua

- **ported**: `source.toml`

## mbedtls/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/mbedtls@source/* .`
- **driven by the cmake build system**: `args=['-DENABLE_PROGRAMS=OFF', '-DENABLE_TESTING=OFF', '-DUSE_SHARED_MBEDTLS_LIBRARY=OFF', '-DUSE_STATIC_MBEDTLS_LIBRARY=ON']`
- **ported**: `generic.toml`

## mbedtls/source.lua

- **ported**: `source.toml`

## meshoptimizer/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/meshoptimizer@source/* .`
- **driven by the cmake build system**: `args=['-DMESHOPT_BUILD_DEMO=OFF', '-DMESHOPT_BUILD_GLTFPACK=OFF', '-DMESHOPT_INSTALL=ON']`
- **ported**: `generic.toml`

## meshoptimizer/source.lua

- **ported**: `source.toml`

## meson/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/lib/python3.14/site-packages`
- **rewrote $OUT to $PREFIX (staging)**: `cp -r mesonbuild $OUT/lib/python3.14/site-packages/`
- **rewrote $OUT to $PREFIX (staging)**: `cp COPYING $OUT/lib/python3.14/site-packages/mesonbuild/COPYING`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/bin`
- **rewrote $OUT to $PREFIX (staging)**: `cp meson.py $OUT/bin/meson`
- **rewrote $OUT to $PREFIX (staging)**: `chmod +x $OUT/bin/meson`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/meson@source/* .`
- **driven by the python build system**: `modules=['mesonbuild'], licenses=['COPYING'], scripts=['meson.py:meson']`
- **ported**: `generic.toml`

## meson/source.lua

- **ported**: `source.toml`

## miniaudio/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/miniaudio@source/* .`
- **driven by the cmake build system**: `args=['-DMINIAUDIO_INSTALL=ON', '-DMINIAUDIO_BUILD_EXAMPLES=OFF', '-DMINIAUDIO_BUILD_TESTS=OFF', '-DMINIAUDIO_BUILD_TOOLS=OFF']`
- **ported**: `generic.toml`

## miniaudio/source.lua

- **ported**: `source.toml`

## minizip/generic.lua

- **left as a shell body (the recipe reports it cannot be built here)**: `generic.lua`
- **ported**: `generic.toml`

## minizip/source.lua

- **ported**: `source.toml`

## minizip-ng/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/minizip-ng@source/* .`
- **driven by the cmake build system**: `args=['-DZLIBNG_PREFER_EXTERNAL=ON', '-DBUILD_SHARED_LIBS=OFF', '-DMZ_FETCH_LIBS=OFF', '-DMZ_FORCE_FETCH_LIBS=OFF', '-DMZ_BUILD_TESTS=OFF', '-DMZ_BUILD_UNIT_TESTS=OFF', '-DMZ_BUILD_FUZZ_TESTS=OFF', '-`
- **ported**: `generic.toml`

## minizip-ng/source.lua

- **ported**: `source.toml`

## mold/clang-native.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/mold@source/* .`
- **driven by the cmake build system**: `args=['-DMOLD_USE_MIMALLOC=OFF']`
- **ported**: `clang-native.toml`

## mold/source.lua

- **ported**: `source.toml`

## mpc/generic.lua

- **rewrote $OUT to $OUTPKG (install prefix)**: `--docdir="$OUT/share/doc/mpc-1.3.1"`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/mpc@source/* .`
- **driven by the autoconf build system**: `configure_args=['--disable-static', '--docdir=$OUTPKG/share/doc/mpc-1.3.1']`
- **ported**: `generic.toml`

## mpc/source.lua

- **ported**: `source.toml`

## mpfr/generic.lua

- **rewrote $OUT to $OUTPKG (install prefix)**: `--docdir="$OUT/share/doc/mpfr-4.2.2"`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/mpfr@source/* .`
- **driven by the autoconf build system**: `configure_args=['--disable-static', '--enable-thread-safe', '--docdir=$OUTPKG/share/doc/mpfr-4.2.2']`
- **ported**: `generic.toml`

## mpfr/source.lua

- **ported**: `source.toml`

## mpg123/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/mpg123@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## mpg123/source.lua

- **ported**: `source.toml`

## msgpack-c/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/msgpack-c@source/* .`
- **driven by the cmake build system**: `args=['-DMSGPACK_BUILD_TESTS=OFF', '-DMSGPACK_BUILD_BENCHMARKS=OFF', '-DMSGPACK_ENABLE_CXX=ON', '-DMSGPACK_ENABLE_C=OFF', '-DBUILD_SHARED_LIBS=OFF']`
- **ported**: `generic.toml`

## msgpack-c/source.lua

- **ported**: `source.toml`

## nanopb/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/nanopb@source/* .`
- **driven by the cmake build system**: `args=['-Dnanopb_BUILD_GENERATOR=OFF', '-DBUILD_STATIC_LIBS=ON', '-DBUILD_SHARED_LIBS=OFF']`
- **ported**: `generic.toml`

## nanopb/source.lua

- **ported**: `source.toml`

## ncurses/generic.lua

- **rewrote $OUT to $OUTPKG (install prefix)**: `--with-pkg-config-libdir=$OUT/lib/pkgconfig \`
- **rewrote $OUT to $PREFIX (staging)**: `ln -sf libncursesw.so $OUT/lib/libcurses.so`
- **rewrote $OUT to $PREFIX (staging)**: `ln -sf libncursesw.so $OUT/lib/libncurses.so`
- **rewrote $OUT to $PREFIX (staging)**: `ln -sf libformw.so $OUT/lib/libform.so`
- **rewrote $OUT to $PREFIX (staging)**: `ln -sf libmenuw.so $OUT/lib/libmenu.so`
- **rewrote $OUT to $PREFIX (staging)**: `ln -sf libpanelw.so $OUT/lib/libpanel.so`
- **rewrote $OUT to $PREFIX (staging)**: `ln -sf ncursesw.pc $OUT/lib/pkgconfig/ncurses.pc`
- **rewrote $OUT to $PREFIX (staging)**: `ln -sf formw.pc $OUT/lib/pkgconfig/form.pc`
- **rewrote $OUT to $PREFIX (staging)**: `ln -sf menuw.pc $OUT/lib/pkgconfig/menu.pc`
- **rewrote $OUT to $PREFIX (staging)**: `ln -sf panelw.pc $OUT/lib/pkgconfig/panel.pc`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/ncurses@source/* .`
- **driven by the autoconf build system**: `configure_args=['--with-shared', '--without-debug', '--without-normal', '--with-cxx-shared', '--enable-pc-files', '--with-pkg-config-libdir=$OUTPKG/lib/pkgconfig', '--disable-stripping']`
- **ported**: `generic.toml`

## ncurses/source.lua

- **ported**: `source.toml`

## nettle/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/nettle@source/* .`
- **driven by the autoconf build system**: `configure_args=['--disable-shared', '--enable-static', '--disable-mini-gmp', '--disable-documentation']`
- **ported**: `generic.toml`

## nettle/source.lua

- **ported**: `source.toml`

## nghttp2/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/nghttp2@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-static', '--disable-shared', '--with-pic', '--disable-app', '--disable-examples', '--disable-tests', '--disable-python-bindings', '--disable-rust-bindings', '--without-libxml`
- **ported**: `generic.toml`

## nghttp2/source.lua

- **ported**: `source.toml`

## ninja/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/bin`
- **rewrote $OUT to $PREFIX (staging)**: `cp ninja $OUT/bin/ninja`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/ninja@source/* .`
- **left as a shell body (installing files is the whole recipe)**: `generic.lua`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/bin`
- **rewrote $OUT to $PREFIX (staging)**: `cp ninja $OUT/bin/ninja`
- **ported**: `generic.toml`

## ninja/source.lua

- **ported**: `source.toml`

## nlohmann-json/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/nlohmann-json@source/* .`
- **driven by the cmake build system**: `args=['-DJSON_BuildTests=OFF']`
- **ported**: `generic.toml`

## nlohmann-json/source.lua

- **ported**: `source.toml`

## oniguruma/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/oniguruma@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-static', '--disable-shared', '--with-pic']`
- **ported**: `generic.toml`

## oniguruma/source.lua

- **ported**: `source.toml`

## openblas/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `CC="$CC" AR="$AR" RANLIB="$RANLIB" PREFIX=$OUT`
- **rewrote $OUT to $PREFIX (staging)**: `CC="$CC" AR="$AR" RANLIB="$RANLIB" PREFIX=$OUT install`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/openblas@source/* .`
- **driven by the make build system**: `make=False, install=False, targets=['$OB_TARGET_ARGS'], make_args=['HOSTCC=cc', 'NOFORTRAN=1', 'NO_SHARED=1', 'PREFIX=$PREFIX']`
- **ported**: `generic.toml`

## openblas/source.lua

- **ported**: `source.toml`

## opencv/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/opencv@source/* .`
- **driven by the cmake build system**: `args=['-DCMAKE_POLICY_VERSION_MINIMUM=3.5', '-DBUILD_SHARED_LIBS=OFF', '-DBUILD_TESTS=OFF', '-DBUILD_PERF_TESTS=OFF', '-DBUILD_EXAMPLES=OFF', '-DBUILD_DOCS=OFF', '-DBUILD_JAVA=OFF', '-DBUILD_OBJC=OFF'`
- **ported**: `generic.toml`

## opencv/source.lua

- **ported**: `source.toml`

## openjpeg/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/openjpeg@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DBUILD_TESTING=OFF', '-DBUILD_CODEC=OFF']`
- **ported**: `generic.toml`

## openjpeg/source.lua

- **ported**: `source.toml`

## openssl/android.lua

- **rewrote $OUT to $OUTPKG (install prefix)**: `./Configure "$ssl_target" -D__ANDROID_API__="$ANDROID_API" --prefix="$OUT" --libdir=lib no-shared no-tests no-docs no-engine no-dso no-dynamic-engine`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/openssl@source/* .`
- **driven by the make build system**: `make=False, install=False, targets=['install_sw']`
- **ported**: `android.toml`

## openssl/generic.lua

- **rewrote $OUT to $OUTPKG (install prefix)**: `./Configure "$ssl_target" --prefix="$OUT" --libdir=lib no-shared no-tests no-docs no-engine no-dso no-dynamic-engine`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/openssl@source/* .`
- **driven by the make build system**: `make=False, install=False, targets=['install_sw']`
- **ported**: `generic.toml`

## openssl/source.lua

- **ported**: `source.toml`

## opus/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/opus@source/* .`
- **driven by the autoconf build system**: `configure_args=['--disable-shared', '--enable-static', '--disable-doc', '--disable-extra-programs']`
- **ported**: `generic.toml`

## opus/source.lua

- **ported**: `source.toml`

## opusfile/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/opusfile@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-static', '--disable-shared', '--with-pic', '--disable-http', '--disable-examples', '--disable-doc']`
- **ported**: `generic.toml`

## opusfile/source.lua

- **ported**: `source.toml`

## p7zip/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/bin`
- **rewrote $OUT to $PREFIX (staging)**: `cp bin/7za $OUT/bin/7za`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/p7zip@source/* .`
- **driven by the make build system**: `make=False, install=False, targets=['7za'], make_args=['CXX=$CXX']`
- **ported**: `generic.toml`

## p7zip/source.lua

- **ported**: `source.toml`

## packaging/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/lib/python3.14/site-packages`
- **rewrote $OUT to $PREFIX (staging)**: `cp -r src/packaging $OUT/lib/python3.14/site-packages/`
- **rewrote $OUT to $PREFIX (staging)**: `cp LICENSE LICENSE.APACHE LICENSE.BSD $OUT/lib/python3.14/site-packages/packaging/`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/packaging@source/* .`
- **driven by the python build system**: `modules=['src/packaging'], licenses=['LICENSE', 'LICENSE.APACHE', 'LICENSE.BSD']`
- **ported**: `generic.toml`

## packaging/source.lua

- **ported**: `source.toml`

## pango/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/pango@source/* .`
- **driven by the meson build system**: `args=['-Dbuildtype=release', '-Ddefault_library=static', '-Dxft=disabled', '-Dlibthai=disabled', '-Dsysprof=disabled', '-Dintrospection=disabled', '-Ddocumentation=false', '-Dman-pages=false', '-Dbuil`
- **ported**: `generic.toml`

## pango/source.lua

- **ported**: `source.toml`

## patch/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/patch@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## patch/source.lua

- **ported**: `source.toml`

## pcre2/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/pcre2@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-static', '--disable-shared', '--with-pic', '--enable-pcre2-8', '--enable-pcre2-16', '--enable-pcre2-32', '--disable-cpp']`
- **ported**: `generic.toml`

## pcre2/source.lua

- **ported**: `source.toml`

## perl/generic.lua

- **rewrote $OUT to $OUTPKG (install prefix)**: `-Dprefix=$OUT \`
- **rewrote $OUT to $OUTPKG (install prefix)**: `-Dvendorprefix=$OUT \`
- **FLAGGED $PREFIX meaning dependencies**: `-Dprivlib=$PREFIX/lib/perl5/5.44/core_perl \`
- **FLAGGED $PREFIX meaning dependencies**: `-Darchlib=$PREFIX/lib/perl5/5.44/core_perl \`
- **FLAGGED $PREFIX meaning dependencies**: `-Dsitelib=$PREFIX/lib/perl5/5.44/site_perl \`
- **FLAGGED $PREFIX meaning dependencies**: `-Dsitearch=$PREFIX/lib/perl5/5.44/site_perl \`
- **FLAGGED $PREFIX meaning dependencies**: `-Dvendorlib=$PREFIX/lib/perl5/5.44/vendor_perl \`
- **FLAGGED $PREFIX meaning dependencies**: `-Dvendorarch=$PREFIX/lib/perl5/5.44/vendor_perl \`
- **rewrote $OUT to $PREFIX (staging)**: `-Dman1dir=$OUT/share/man/man1 \`
- **rewrote $OUT to $PREFIX (staging)**: `-Dman3dir=$OUT/share/man/man3 \`

## perl/generic.toml

- **fixed by hand (perl bakes these paths in with no relocation, so they must be the final ones)**: `-D(privlib|archlib|sitelib|sitearch|vendorlib|vendorarch)=\$\{RETROLUNAR_PORT_PREFIX\}`

## perl/generic.lua

- **driven by the make build system**: `no arguments`
- **ported**: `generic.toml`

## perl/source.lua

- **ported**: `source.toml`

## physfs/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/physfs@source/* .`
- **driven by the cmake build system**: `args=['-DPHYSFS_BUILD_STATIC=ON', '-DPHYSFS_BUILD_SHARED=OFF', '-DPHYSFS_BUILD_TEST=OFF', '-DPHYSFS_BUILD_DOCS=OFF', '-DPHYSFS_DISABLE_INSTALL=OFF']`
- **ported**: `generic.toml`

## physfs/source.lua

- **ported**: `source.toml`

## pixman/android.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/pixman@source/* .`
- **driven by the meson build system**: `args=['-Dbuildtype=release', '-Ddefault_library=static', '-Dtests=disabled', '-Ddemos=disabled', '-Dlibpng=disabled', '-Dgtk=disabled', '-Dopenmp=disabled', '-Darm-simd=disabled', '-Dneon=disabled']`
- **ported**: `android.toml`

## pixman/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/pixman@source/* .`
- **driven by the meson build system**: `args=['-Dbuildtype=release', '-Ddefault_library=static', '-Dtests=disabled', '-Ddemos=disabled', '-Dlibpng=disabled', '-Dgtk=disabled', '-Dopenmp=disabled']`
- **ported**: `generic.toml`

## pixman/source.lua

- **ported**: `source.toml`

## pkgconf/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/pkgconf@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## pkgconf/source.lua

- **ported**: `source.toml`

## plog/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/plog@source/* .`
- **driven by the cmake build system**: `args=['-DPLOG_BUILD_SAMPLES=OFF', '-DPLOG_BUILD_TESTS=OFF', '-DPLOG_INSTALL=ON']`
- **ported**: `generic.toml`

## plog/source.lua

- **ported**: `source.toml`

## pngprobe/generic.lua

- **FLAGGED $PREFIX meaning dependencies**: `echo "error: pngprobe did not link libpng16 from \$PREFIX" >&2`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p "$OUT/bin"`
- **rewrote $OUT to $PREFIX (staging)**: `cp "$_bin" "$OUT/bin/"`

## pngprobe/generic.toml

- **fixed by hand (a message, not a path)**: `\\?\$\{RETROLUNAR_PORT_PREFIX\}`

## pngprobe/generic.lua

- **driven by the cargo build system**: `env=PNG_CONFIG=false, bin=pngprobe`
- **ported**: `generic.toml`

## portaudio/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/portaudio@source/* .`
- **driven by the cmake build system**: `args=['-DPA_BUILD_STATIC=ON', '-DPA_BUILD_SHARED=OFF', '-DPA_USE_ALSA=OFF', '-DPA_USE_JACK=OFF', '-DPA_BUILD_TESTS=OFF', '-DPA_BUILD_EXAMPLES=OFF']`
- **ported**: `generic.toml`

## portaudio/source.lua

- **ported**: `source.toml`

## procps/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/procps@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## procps/source.lua

- **ported**: `source.toml`

## protobuf/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/protobuf@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-Dprotobuf_BUILD_SHARED_LIBS=OFF', '-Dprotobuf_BUILD_PROTOC_BINARIES=OFF', '-Dprotobuf_BUILD_LIBUPB=OFF', '-Dprotobuf_BUILD_TESTS=OFF', '-Dprotobuf_BUILD_CONFORMANCE=`
- **ported**: `generic.toml`

## protobuf/source.lua

- **ported**: `source.toml`

## protobuf-c/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/protobuf-c@source/* .`
- **driven by the autoconf build system**: `configure_args=['--enable-static', '--disable-shared', '--with-pic', '--disable-protoc']`
- **ported**: `generic.toml`

## protobuf-c/source.lua

- **ported**: `source.toml`

## psmisc/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/psmisc@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## psmisc/source.lua

- **ported**: `source.toml`

## pugixml/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/pugixml@source/* .`
- **driven by the cmake build system**: `args=['-DPUGIXML_BUILD_TESTS=OFF', '-DBUILD_SHARED_LIBS=OFF']`
- **ported**: `generic.toml`

## pugixml/source.lua

- **ported**: `source.toml`

## python/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/python@source/* .`
- **driven by the autoconf build system**: `configure_args=['--with-build-python=python3', '--disable-shared', '--without-ensurepip', '--disable-test-modules']`
- **ported**: `generic.toml`

## python/source.lua

- **ported**: `source.toml`

## ragel/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/ragel@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## ragel/source.lua

- **ported**: `source.toml`

## range-v3/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/range-v3@source/* .`
- **driven by the cmake build system**: `args=['-DRANGE_V3_TESTS=OFF', '-DRANGE_V3_EXAMPLES=OFF', '-DRANGE_V3_DOCS=OFF', '-DRANGE_V3_PERF=OFF', '-DRANGE_V3_HEADER_CHECKS=OFF']`
- **ported**: `generic.toml`

## range-v3/source.lua

- **ported**: `source.toml`

## rapidjson/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/rapidjson@source/* .`
- **driven by the cmake build system**: `args=['-DRAPIDJSON_BUILD_DOC=OFF', '-DRAPIDJSON_BUILD_EXAMPLES=OFF', '-DRAPIDJSON_BUILD_TESTS=OFF']`
- **ported**: `generic.toml`

## rapidjson/source.lua

- **ported**: `source.toml`

## raylib/android.lua

- **rewrote $OUT to $PREFIX (staging)**: `' "$OUT/lib/pkgconfig/raylib.pc" > "$WORK/raylib.pc"`
- **rewrote $OUT to $PREFIX (staging)**: `cp "$WORK/raylib.pc" "$OUT/lib/pkgconfig/raylib.pc"`
- **rewrote $OUT to $PREFIX (staging)**: `' "$OUT/lib/cmake/raylib/raylib-targets.cmake" > "$WORK/raylib-targets.cmake"`
- **rewrote $OUT to $PREFIX (staging)**: `cp "$WORK/raylib-targets.cmake" "$OUT/lib/cmake/raylib/raylib-targets.cmake"`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/raylib@source/* .`
- **driven by the cmake build system**: `args=['-DCMAKE_BUILD_TYPE=Release', '-DPLATFORM=Android', '-DANDROID_NDK=$NDK', '-DBUILD_EXAMPLES=OFF']`
- **ported**: `android.toml`

## raylib/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/raylib@source/* .`
- **driven by the cmake build system**: `args=['-DCMAKE_BUILD_TYPE=Release', '-DBUILD_EXAMPLES=OFF']`
- **ported**: `generic.toml`

## raylib/source.lua

- **ported**: `source.toml`

## re2c/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/re2c@source/* .`
- **driven by the cmake build system**: `args=['-DRE2C_BUILD_TESTS=OFF']`
- **ported**: `generic.toml`

## re2c/source.lua

- **ported**: `source.toml`

## readline/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/readline@source/* .`
- **driven by the autoconf build system**: `configure_args=['--disable-shared', '--enable-static', '--without-curses']`
- **ported**: `generic.toml`

## readline/source.lua

- **ported**: `source.toml`

## samurai/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `make install PREFIX="$OUT"`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/samurai@source/* .`
- **driven by the make build system**: `make=False, install=False, make_args=['PREFIX=$PREFIX']`
- **ported**: `generic.toml`

## samurai/source.lua

- **ported**: `source.toml`

## sdl2/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/sdl2@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DSDL_SHARED=OFF', '-DSDL_STATIC=ON', '-DSDL_TEST=OFF', '-DSDL_TESTS=OFF', '-DSDL_EXAMPLES=OFF', '-DSDL_INSTALL_TESTS=OFF', '-DSDL_SYSTEM_ICONV=OFF', '-DSDL_LIBC=ON',`
- **ported**: `generic.toml`

## sdl2/source.lua

- **ported**: `source.toml`

## sed/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/sed@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## sed/source.lua

- **ported**: `source.toml`

## setuptools/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/lib/python3.14/site-packages`
- **rewrote $OUT to $PREFIX (staging)**: `cp -r $NESTDIR/source/setuptools/* $OUT/lib/python3.14/site-packages/`
- **driven by the python build system**: `whole_tree=True`
- **ported**: `generic.toml`

## setuptools/source.lua

- **ported**: `source.toml`

## sevenzip/android.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/bin`
- **rewrote $OUT to $PREFIX (staging)**: `cp CPP/7zip/Bundles/Alone2/_o/7zz $OUT/bin/7zz`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/sevenzip@source/* .`
- **driven by the make build system**: `make=False, install=False, targets=['CPP/7zip/Bundles/Alone2', 'makefile.gcc'], make_args=['-C', '-f', '-j1', 'CXX=$CXX', 'CFLAGS_BASE2=$CFLAGS', 'CXXFLAGS_BASE2=$CXXFLAGS', 'CFLAGS_WARN_WALL=-Wall -W`
- **ported**: `android.toml`

## sevenzip/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/bin`
- **rewrote $OUT to $PREFIX (staging)**: `cp CPP/7zip/Bundles/Alone2/_o/7zz $OUT/bin/7zz`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/sevenzip@source/* .`
- **driven by the make build system**: `make=False, install=False, targets=['CPP/7zip/Bundles/Alone2', 'makefile.gcc'], make_args=['-C', '-f', 'CXX=$CXX', 'CFLAGS_BASE2=$CFLAGS', 'CXXFLAGS_BASE2=$CXXFLAGS', 'CFLAGS_WARN_WALL=-Wall -Wextra']`
- **ported**: `generic.toml`

## sevenzip/source.lua

- **ported**: `source.toml`

## shadow/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/shadow@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## shadow/source.lua

- **ported**: `source.toml`

## simdjson/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/simdjson@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF']`
- **ported**: `generic.toml`

## simdjson/source.lua

- **ported**: `source.toml`

## snappy/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/snappy@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DSNAPPY_BUILD_TESTS=OFF', '-DSNAPPY_BUILD_BENCHMARKS=OFF']`
- **ported**: `generic.toml`

## snappy/source.lua

- **ported**: `source.toml`

## soundtouch/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/soundtouch@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DSOUNDSTRETCH=OFF', '-DSOUNDTOUCH_DLL=OFF']`
- **ported**: `generic.toml`

## soundtouch/source.lua

- **ported**: `source.toml`

## soxr/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/soxr@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DBUILD_TESTS=OFF', '-DBUILD_EXAMPLES=OFF', '-DBUILD_LSR_TESTS=OFF', '-DWITH_OPENMP=OFF']`
- **ported**: `generic.toml`

## soxr/source.lua

- **ported**: `source.toml`

## spdlog/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/spdlog@source/* .`
- **driven by the cmake build system**: `args=['-DSPDLOG_BUILD_EXAMPLE=OFF', '-DSPDLOG_BUILD_EXAMPLE_HOOK=OFF', '-DSPDLOG_BUILD_TESTS=OFF', '-DSPDLOG_BUILD_BENCH=OFF', '-DSPDLOG_FMT_EXTERNAL=ON', '-DBUILD_SHARED_LIBS=OFF', '-DSPDLOG_INSTALL=`
- **ported**: `generic.toml`

## spdlog/source.lua

- **ported**: `source.toml`

## sqlite/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/sqlite@source/* .`
- **driven by the autoconf build system**: `configure_args=['--disable-shared', '--enable-static']`
- **ported**: `generic.toml`

## sqlite/source.lua

- **ported**: `source.toml`

## squashfs-tools/android.lua

- **rewrote $OUT to $OUTPKG (install prefix)**: `make -j"$CORES" LZO_SUPPORT=0 USE_PREBUILT_MANPAGES=y INSTALL_PREFIX="$OUT" \`
- **rewrote $OUT to $OUTPKG (install prefix)**: `make -j"$CORES" LZO_SUPPORT=0 USE_PREBUILT_MANPAGES=y INSTALL_PREFIX="$OUT" \`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/squashfs-tools@source/* .`
- **driven by the make build system**: `make=False, install=False, make_args=['LZO_SUPPORT=0', 'USE_PREBUILT_MANPAGES=y', 'INSTALL_PREFIX=$OUTPKG', 'LIBS=-lm -lz -llz4 -llzma -lzstd']`
- **ported**: `android.toml`

## squashfs-tools/generic.lua

- **rewrote $OUT to $OUTPKG (install prefix)**: `make -j"$CORES" LZO_SUPPORT=0 USE_PREBUILT_MANPAGES=y INSTALL_PREFIX="$OUT"`
- **rewrote $OUT to $OUTPKG (install prefix)**: `make -j"$CORES" LZO_SUPPORT=0 USE_PREBUILT_MANPAGES=y INSTALL_PREFIX="$OUT" install`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/squashfs-tools@source/* .`
- **driven by the make build system**: `make=False, install=False, make_args=['LZO_SUPPORT=0', 'USE_PREBUILT_MANPAGES=y', 'INSTALL_PREFIX=$OUTPKG']`
- **ported**: `generic.toml`

## squashfs-tools/source.lua

- **ported**: `source.toml`

## stb/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/include`
- **rewrote $OUT to $PREFIX (staging)**: `cp stb*.h stb_vorbis.c LICENSE $OUT/include/`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/stb@source/* .`
- **left as a shell body (installing files is the whole recipe)**: `generic.lua`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/include`
- **rewrote $OUT to $PREFIX (staging)**: `cp stb*.h stb_vorbis.c LICENSE $OUT/include/`
- **ported**: `generic.toml`

## stb/source.lua

- **ported**: `source.toml`

## strace/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/strace@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## strace/source.lua

- **ported**: `source.toml`

## swig/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/swig@source/* .`
- **driven by the cmake build system**: `args=['-DWITH_PCRE=ON']`
- **ported**: `generic.toml`

## swig/source.lua

- **ported**: `source.toml`

## sysklogd/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/sysklogd@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## sysklogd/source.lua

- **ported**: `source.toml`

## systemd-man-pages/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/share/man`
- **rewrote $OUT to $PREFIX (staging)**: `cp -r $NESTDIR/source/systemd-man-pages/* $OUT/share/man/`
- **left as a shell body (installing files is the whole recipe)**: `generic.lua`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/share/man`
- **rewrote $OUT to $PREFIX (staging)**: `cp -r $NESTDIR/source/systemd-man-pages/* $OUT/share/man/`
- **ported**: `generic.toml`

## systemd-man-pages/source.lua

- **ported**: `source.toml`

## sysvinit/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `make install ROOT="$OUT" usrdir=`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/sysvinit@source/* .`
- **driven by the make build system**: `make=False, install=False, make_args=['ROOT=$PREFIX', 'usrdir=']`
- **ported**: `generic.toml`

## sysvinit/source.lua

- **ported**: `source.toml`

## tar/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/tar@source/* .`
- **driven by the autoconf build system**: `no arguments`
- **ported**: `generic.toml`

## tar/source.lua

- **ported**: `source.toml`

## tbb/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/tbb@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DTBB_TEST=OFF', '-DTBB_STRICT=OFF', '-DTBB_ENABLE_IPO=OFF']`
- **ported**: `generic.toml`

## tbb/source.lua

- **ported**: `source.toml`

## tcl/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `./unix/configure $AUTOCONF_CONFIGURE_FLAGS --mandir="$OUT/share/man" --disable-rpath`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/tcl@source/* .`
- **driven by the make build system**: `targets=['install-private-headers']`
- **ported**: `generic.toml`

## tcl/source.lua

- **ported**: `source.toml`

## tcl-docs/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/share/doc/tcl8.6.18`
- **rewrote $OUT to $PREFIX (staging)**: `cp -r $NESTDIR/source/tcl-docs/* $OUT/share/doc/tcl8.6.18/`
- **left as a shell body (installing files is the whole recipe)**: `generic.lua`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/share/doc/tcl8.6.18`
- **rewrote $OUT to $PREFIX (staging)**: `cp -r $NESTDIR/source/tcl-docs/* $OUT/share/doc/tcl8.6.18/`
- **ported**: `generic.toml`

## tcl-docs/source.lua

- **ported**: `source.toml`

## termcap/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/lib/pkgconfig`
- **rewrote $OUT to $OUTPKG (install prefix)**: `printf 'prefix=%s\nexec_prefix=${prefix}\nlibdir=${exec_prefix}/lib\nincludedir=${prefix}/include\nName: termcap\nDescription: GNU termcap\nVersion: 1.3.1\nLibs: -L${libdir} -ltermcap\nCflags: -I${inc`
- **FLAGGED $PREFIX meaning dependencies**: `printf 'prefix=%s\nexec_prefix=${prefix}\nlibdir=${exec_prefix}/lib\nincludedir=${prefix}/include\nName: termcap\nDescription: GNU termcap\nVersion: 1.3.1\nLibs: -L${libdir} -ltermcap\nCflags: -I${inc`

## termcap/generic.toml

- **fixed by hand (the .pc file has to record the final install path)**: `\$\{RETROLUNAR_PORT_PREFIX\}"`

## termcap/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/termcap@source/* .`
- **driven by the autoconf build system**: `configure_args=['--disable-shared', '--enable-static']`
- **ported**: `generic.toml`

## termcap/source.lua

- **ported**: `source.toml`

## texinfo/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/texinfo@source/* .`
- **driven by the make build system**: `no arguments`
- **ported**: `generic.toml`

## texinfo/source.lua

- **ported**: `source.toml`

## tinyexr/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/lib $OUT/include`
- **rewrote $OUT to $PREFIX (staging)**: `cp build/lib/libtinyexr.a $OUT/lib/`
- **rewrote $OUT to $PREFIX (staging)**: `cp tinyexr.h exr_reader.hh streamreader.hh $OUT/include/`
- **rewrote $OUT to $PREFIX (staging)**: `cp deps/miniz/miniz.h $OUT/include/`
- **rewrote $OUT to $PREFIX (staging)**: `cp build/libminiz.a $OUT/lib/`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/tinyexr@source/* .`
- **driven by the cmake build system**: `args=['-DTINYEXR_BUILD_SAMPLE=OFF', '-DTINYEXR_USE_MINIZ=ON']`
- **ported**: `generic.toml`

## tinyexr/source.lua

- **ported**: `source.toml`

## tinyxml2/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/tinyxml2@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-Dtinyxml2_BUILD_TOOLS=OFF', '-Dtinyxml2_BUILD_TESTING=OFF', '-Dtinyxml2_INSTALL=ON']`
- **ported**: `generic.toml`

## tinyxml2/source.lua

- **ported**: `source.toml`

## tl-expected/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/tl-expected@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_TESTING=OFF', '-DEXPECTED_BUILD_TESTS=OFF', '-DEXPECTED_BUILD_PACKAGE=OFF']`
- **ported**: `generic.toml`

## tl-expected/source.lua

- **ported**: `source.toml`

## toml11/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/toml11@source/* .`
- **driven by the cmake build system**: `args=['-DTOML11_BUILD_TESTS=OFF']`
- **ported**: `generic.toml`

## toml11/source.lua

- **ported**: `source.toml`

## tomlplusplus/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/tomlplusplus@source/* .`
- **driven by the cmake build system**: `args=['-DTOMLPLUSPLUS_BUILD_TESTS=OFF']`
- **ported**: `generic.toml`

## tomlplusplus/source.lua

- **ported**: `source.toml`

## tzdata/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `make ZIC=zic TOPDIR="$OUT/usr" install`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/tzdata@source/* .`
- **driven by the make build system**: `make=False, install=False, make_args=['ZIC=zic', 'TOPDIR=$PREFIX/usr']`
- **ported**: `generic.toml`

## tzdata/source.lua

- **ported**: `source.toml`

## udev-lfs/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/lib/udev/rules.d`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/lib/udev/rules.d/network`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/usr/share/doc/udev-20230818`
- **rewrote $OUT to $PREFIX (staging)**: `cp *.rules $OUT/lib/udev/rules.d/`
- **rewrote $OUT to $PREFIX (staging)**: `cp *.txt $OUT/usr/share/doc/udev-20230818/`
- **rewrote $OUT to $PREFIX (staging)**: `cp init-net-rules.sh rule_generator.functions $OUT/usr/share/doc/udev-20230818/`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/usr/share/udev`
- **rewrote $OUT to $PREFIX (staging)**: `cp write_cd_rules write_net_rules $OUT/usr/share/udev/`
- **left as a shell body (installing files is the whole recipe)**: `generic.lua`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/lib/udev/rules.d`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/lib/udev/rules.d/network`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/usr/share/doc/udev-20230818`
- **rewrote $OUT to $PREFIX (staging)**: `cp *.rules $OUT/lib/udev/rules.d/`
- **rewrote $OUT to $PREFIX (staging)**: `cp *.txt $OUT/usr/share/doc/udev-20230818/`
- **rewrote $OUT to $PREFIX (staging)**: `cp init-net-rules.sh rule_generator.functions $OUT/usr/share/doc/udev-20230818/`
- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/usr/share/udev`
- **rewrote $OUT to $PREFIX (staging)**: `cp write_cd_rules write_net_rules $OUT/usr/share/udev/`
- **ported**: `generic.toml`

## udev-lfs/source.lua

- **ported**: `source.toml`

## uncrustify/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/uncrustify@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_TESTING=OFF']`
- **ported**: `generic.toml`

## uncrustify/source.lua

- **ported**: `source.toml`

## universal-ctags/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/universal-ctags@source/* .`
- **driven by the autoconf build system**: `configure_args=['--disable-external-sort', '--disable-xml', '--disable-json', '--disable-yaml', '--disable-seccomp', '--disable-pcre2']`
- **ported**: `generic.toml`

## universal-ctags/source.lua

- **ported**: `source.toml`

## utf8proc/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/utf8proc@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF']`
- **ported**: `generic.toml`

## utf8proc/source.lua

- **ported**: `source.toml`

## util-linux/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/util-linux@source/* .`
- **driven by the autoconf build system**: `configure_args=['--without-cap-ng', '--disable-asciidoc', '--disable-pylibmount', '--disable-liblastlog2', '--disable-libuuid', '--disable-more', '--disable-vipw', '--disable-nls']`
- **ported**: `generic.toml`

## util-linux/source.lua

- **ported**: `source.toml`

## vim/generic.lua

- **added a dependency v1 used implicitly**: `ncurses`
- **rewrote $OUT to $OUTPKG (install prefix)**: `./configure --prefix="$OUT" \`
- **FLAGGED $PREFIX meaning dependencies**: `--with-tlibdir="$PREFIX/lib"`

## vim/generic.toml

- **fixed by hand (v1 took ncurses from the shared prefix and declared no dependency; v2 cannot)**: `--with-tlibdir="\$\{RETROLUNAR_PORT_PREFIX\}/lib"`

## vim/generic.lua

- **driven by the autoconf build system**: `configure_args=['--prefix=$OUTPKG', '--host=$HOST_TRIPLET', '--with-features=normal', '--enable-multibyte', '--with-tlibdir=$ncurses_PREFIX/lib']`
- **ported**: `generic.toml`

## vim/source.lua

- **ported**: `source.toml`

## vulkan-headers/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/vulkan-headers@source/* .`
- **driven by the cmake build system**: `args=['-DVULKAN_HEADERS_ENABLE_TESTS=OFF', '-DVULKAN_HEADERS_ENABLE_INSTALL=ON', '-DVULKAN_HEADERS_ENABLE_MODULE=OFF']`
- **ported**: `generic.toml`

## vulkan-headers/source.lua

- **ported**: `source.toml`

## wheel/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `mkdir -p $OUT/lib/python3.14/site-packages`
- **rewrote $OUT to $PREFIX (staging)**: `cp -r src/wheel $OUT/lib/python3.14/site-packages/`
- **rewrote $OUT to $PREFIX (staging)**: `cp LICENSE.txt $OUT/lib/python3.14/site-packages/wheel/LICENSE.txt`
- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/wheel@source/* .`
- **driven by the python build system**: `modules=['src/wheel'], licenses=['LICENSE.txt']`
- **ported**: `generic.toml`

## wheel/source.lua

- **ported**: `source.toml`

## wolfssl/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/wolfssl@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DWOLFSSL_EXAMPLES=no', '-DWOLFSSL_CRYPT_TESTS=no', '-DWOLFSSL_OPENSSLEXTRA=yes']`
- **ported**: `generic.toml`

## wolfssl/source.lua

- **ported**: `source.toml`

## xml-parser/generic.lua

- **FLAGGED $PREFIX meaning dependencies**: `perl Makefile.PL EXPATINCPATH=$PREFIX/include EXPATLIBPATH=$PREFIX/lib`

## xml-parser/generic.toml

- **fixed by hand (expat is a declared dependency)**: `EXPATINCPATH=\$\{RETROLUNAR_PORT_PREFIX\}/include`
- **fixed by hand (expat is a declared dependency)**: `EXPATLIBPATH=\$\{RETROLUNAR_PORT_PREFIX\}/lib`

## xml-parser/generic.lua

- **driven by the make build system**: `make=False, install=False, make_args=['LD=$LD', 'OPTIMIZE=$CFLAGS', 'perl_inc=$NATIVE_PREFIX/lib/perl5/5.44/core_perl', 'to_cflags=-D_I_CRYPT_H=0 -DHAS_UNION_SEMUN=1']`
- **ported**: `generic.toml`

## xml-parser/source.lua

- **ported**: `source.toml`

## xtensor/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/xtensor@source/* .`
- **driven by the cmake build system**: `no arguments`
- **ported**: `generic.toml`

## xtensor/source.lua

- **ported**: `source.toml`

## xxhash/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/xxhash@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF'], source_dir=cmake_unofficial`
- **ported**: `generic.toml`

## xxhash/source.lua

- **ported**: `source.toml`

## xz/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/xz@source/* .`
- **driven by the autoconf build system**: `configure_args=['--disable-nls', '--disable-shared', '--disable-unxz', '--disable-lzmadec', '--disable-lzmainfo', '--disable-lzlinks', '--disable-scripts', '--disable-doc']`
- **ported**: `generic.toml`

## xz/source.lua

- **ported**: `source.toml`

## yajl/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/yajl@source/* .`
- **driven by the cmake build system**: `no arguments`
- **ported**: `generic.toml`

## yajl/source.lua

- **ported**: `source.toml`

## yaml-cpp/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/yaml-cpp@source/* .`
- **driven by the cmake build system**: `args=['-DYAML_CPP_BUILD_TESTS=OFF', '-DYAML_CPP_BUILD_TOOLS=OFF', '-DYAML_CPP_BUILD_UTILS=OFF', '-DYAML_BUILD_SHARED_LIBS=OFF', '-DYAML_CPP_INSTALL=ON']`
- **ported**: `generic.toml`

## yaml-cpp/source.lua

- **ported**: `source.toml`

## zlib/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/zlib@source/* .`
- **driven by the cmake build system**: `args=['-DZLIB_BUILD_EXAMPLES=OFF']`
- **ported**: `generic.toml`

## zlib/source.lua

- **ported**: `source.toml`

## zlib/mingw64.toml

- **written from the port's own notes**: `v1 had no separate file for this system`

## zlib-ng/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/zlib-ng@source/* .`
- **driven by the cmake build system**: `args=['-DZLIB_COMPAT=OFF', '-DZLIB_ENABLE_TESTS=OFF', '-DBUILD_SHARED_LIBS=OFF']`
- **ported**: `generic.toml`

## zlib-ng/source.lua

- **ported**: `source.toml`

## zopfli/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/zopfli@source/* .`
- **driven by the cmake build system**: `args=['-DZOPFLI_BUILD_SHARED=OFF']`
- **ported**: `generic.toml`

## zopfli/source.lua

- **ported**: `source.toml`

## zstd/generic.lua

- **rewrote $OUT to $PREFIX (staging)**: `make -C lib PREFIX="$OUT" LIBDIR="$OUT/lib" HAVE_LZMA=0 HAVE_ZLIB=0 ZLIB_PREFIX="$PREFIX"`
- **FLAGGED $PREFIX meaning dependencies**: `make -C lib PREFIX="$OUT" LIBDIR="$OUT/lib" HAVE_LZMA=0 HAVE_ZLIB=0 ZLIB_PREFIX="$PREFIX"`
- **rewrote $OUT to $PREFIX (staging)**: `make -C lib PREFIX="$OUT" LIBDIR="$OUT/lib" HAVE_LZMA=0 HAVE_ZLIB=0 ZLIB_PREFIX="$PREFIX" install`
- **FLAGGED $PREFIX meaning dependencies**: `make -C lib PREFIX="$OUT" LIBDIR="$OUT/lib" HAVE_LZMA=0 HAVE_ZLIB=0 ZLIB_PREFIX="$PREFIX" install`
- **rewrote $OUT to $PREFIX (staging)**: `make -C programs PREFIX="$OUT" HAVE_LZMA=0 HAVE_ZLIB=0 ZLIB_PREFIX="$PREFIX"`
- **FLAGGED $PREFIX meaning dependencies**: `make -C programs PREFIX="$OUT" HAVE_LZMA=0 HAVE_ZLIB=0 ZLIB_PREFIX="$PREFIX"`
- **rewrote $OUT to $PREFIX (staging)**: `make -C programs PREFIX="$OUT" HAVE_LZMA=0 HAVE_ZLIB=0 ZLIB_PREFIX="$PREFIX" install`
- **FLAGGED $PREFIX meaning dependencies**: `make -C programs PREFIX="$OUT" HAVE_LZMA=0 HAVE_ZLIB=0 ZLIB_PREFIX="$PREFIX" install`

## zstd/generic.toml

- **fixed by hand (an install prefix: the final path, DESTDIR redirects the write)**: `PREFIX="\$\{RETROLUNAR_PORT_PREFIX\}"`
- **fixed by hand (an install prefix: the final path, DESTDIR redirects the write)**: `LIBDIR="\$\{RETROLUNAR_PORT_PREFIX\}/lib"`

## zstd/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/zstd@source/* .`
- **driven by the make build system**: `make=False, install=False, targets=['programs'], make_args=['-C', 'PREFIX=$OUTPKG', 'HAVE_LZMA=0', 'HAVE_ZLIB=0', 'ZLIB_PREFIX=$OUTPKG']`
- **ported**: `generic.toml`

## zstd/source.lua

- **ported**: `source.toml`

## zziplib/generic.lua

- **dropped (the tool copies @source trees in)**: `cp -r $NESTDIR/zziplib@source/* .`
- **driven by the cmake build system**: `args=['-DBUILD_SHARED_LIBS=OFF', '-DZZIPFSEEKO=OFF', '-DZZIP_COMPAT=OFF', '-DZZIPSDL=OFF', '-DZZIPWRAP=OFF', '-DZZIPBINS=OFF', '-DZZIPTEST=OFF', '-DZZIPDOCS=OFF']`
- **ported**: `generic.toml`

## zziplib/source.lua

- **ported**: `source.toml`

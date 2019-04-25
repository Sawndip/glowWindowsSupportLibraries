# glowWindowsSupportLibraries

Modified libpng so that it includes zlib in Visual studio soluiton, and it all can be build together. 
Tested with Visual Studio 2017 to build libpng dll.
All the pre-build binaries are checked in, but if they need to be re-build from source instructions below:

Example of command:

ZLIB/LIBPNG
cmake -G "Visual Studio 15 2017" -DCMAKE_GENERATOR_PLATFORM=x64 -DPNG_BUILD_ZLIB=ON -DZLIB_INCLUDE_DIR="../zlib-1.2.11" -DPNG_STATIC=OFF -DPNG_SHARED=ON -DCMAKE_INSTALL_PREFIX:PATH=../libpngInstall ..\lpng1636

cmake --build . --config Debug
cmake --build . --config Release
cmake --build . --target install --config Debug
cmake --build . --target install --config Release


GLOG
cmake ../ -DCMAKE_GENERATOR_PLATFORM=x64 -DCMAKE_INSTALL_RUNSTATEDIR:PATH="" -DCMAKE_INSTALL_PREFIX:PATH="<Glog_Location>" -DWITH_GFLAGS:BOOL="0"

cmake --build . --config Release
cmake --build . --config Debug
cmake --build . --target install --config Debug
cmake --build . --target install --config Release

Protobuf
When running config it will give a warning that zlib is not found. This is doesn't impact GLOW.
cmake ..\cmake -DBUILD_SHARED_LIBS=TRUE -Dprotobuf_BUILD_TESTS=OFF -DCMAKE_GENERATOR_PLATFORM=x64 -DCMAKE_INSTALL_PREFIX:PATH=../protobufInstall

cmake --build . --config Debug
cmake --build . --config Release
cmake --build . --target install --config Debug
cmake --build . --target install --config Release

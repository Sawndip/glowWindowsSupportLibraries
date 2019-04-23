# glowWindowsSupportLibraries

Modified libpng so that it includes zlib in Visual studio soluiton, and it all can be build together. 
Tested with Visual Studio 2017 to build libpng dll.

Example of command:
cmake -G "Visual Studio 15 2017" -DCMAKE_GENERATOR_PLATFORM=x64 -DPNG_BUILD_ZLIB=ON -DZLIB_INCLUDE_DIR="../zlib-1.2.11" -DPNG_STATIC=OFF -DPNG_SHARED=ON ..\lpng1636

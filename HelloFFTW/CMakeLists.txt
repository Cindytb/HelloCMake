cmake_minimum_required (VERSION 3.8)

# Add include directories & libraries
if (WIN32)   
  set ( PROJECT_LINK_LIBS libsndfile-1.lib libfftw3f-3.lib)
  link_directories("D:\\Visual Studio Dependences\\lib")
  include_directories("D:\\Visual Studio Dependences\\include")
else (WIN32)
  set(PROJECT_LINK_LIBS sndfile.so fftw3f.so)
  link_directories("/usr/lib/x86_64-linux-gnu")
  include_directories("/usr/include")
endif (WIN32)
# Compile
add_executable (HelloFFTW "HelloFFTW.cpp")

# Add to linker
target_link_libraries(HelloFFTW ${PROJECT_LINK_LIBS} )

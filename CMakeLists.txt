project(oboe_src)
cmake_minimum_required(VERSION 3.0)
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_library(oboe_src STATIC
        src/IntegerRatio.cpp
        src/LinearResampler.cpp
        src/MultiChannelResampler.cpp
        src/PolyphaseResampler.cpp
        src/PolyphaseResamplerMono.cpp
        src/PolyphaseResamplerStereo.cpp
        src/SincResampler.cpp
        src/SincResamplerStereo.cpp
    )

target_include_directories(oboe_src PUBLIC include/oboe_src)
target_include_directories(oboe_src INTERFACE include)

install(TARGETS oboe_src ARCHIVE DESTINATION lib)
file(GLOB PUBLIC_HEADERS include/oboe_src/*.h)
install(FILES ${PUBLIC_HEADERS} DESTINATION include/oboe_src)

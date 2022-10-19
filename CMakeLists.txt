add_library(fastled STATIC
    src/FastLED.cpp
    src/colorpalettes.cpp
    src/hsv2rgb.cpp
    src/noise.cpp
    src/power_mgt.cpp
    src/bitswap.cpp
    src/colorutils.cpp
    src/lib8tion.cpp
    src/platforms.cpp
    src/wiring.cpp
    # src/FastLED.h
)
target_compile_options(fastled
    PUBLIC $<$<COMPILE_LANGUAGE:CXX>:-Wno-register>
)
target_link_libraries(fastled
    pico_stdlib
    hardware_pio
    hardware_dma
)
target_include_directories(fastled SYSTEM
    PUBLIC src
)
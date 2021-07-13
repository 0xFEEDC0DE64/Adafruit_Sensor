set(headers
    Adafruit_Sensor.h
)

set(sources
    Adafruit_Sensor.cpp
)

set(dependencies
    arduino-esp32
    espchrono
)

idf_component_register(
    INCLUDE_DIRS
        .
    SRCS
        ${headers}
        ${sources}
    REQUIRES
        ${dependencies}
)

target_compile_options(${COMPONENT_TARGET}
    PRIVATE
        -fstack-reuse=all
        -fstack-protector-all
        -Wno-unused-function
        -Wno-deprecated-declarations
        -Wno-missing-field-initializers
        -Wno-parentheses
)

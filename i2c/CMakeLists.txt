cmake_minimum_required(VERSION 3.16)

project(Adafruit_BNO055 VERSION 0.0.1)

SET(NOT_ARDUINO TRUE)

add_library(${CMAKE_PROJECT_NAME}_lib STATIC
              src/Adafruit_BNO055.cpp
              src/Adafruit_Sensor.cpp
              )

target_include_directories(${CMAKE_PROJECT_NAME}_lib PUBLIC include)
target_compile_definitions(${CMAKE_PROJECT_NAME}_lib
     PRIVATE NOT_ARDUINO
   )

add_executable(read_from_sensor read_from_sensor.cpp)
target_link_libraries(read_from_sensor PUBLIC {$PROJECT_NAME}_lib)

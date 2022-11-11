cmake_minimum_required(VERSION 3.2.2)
project(ArduinoFake VERSION 0.1)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

LIST(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_LIST_DIR}/cmake)

# Include external libs
add_subdirectory(external)

# Targets that we develop here
enable_testing()

add_subdirectory(src)

if(${CMAKE_PROJECT_NAME} EQUAL ${PROJECT_NAME})
  add_subdirectory(test)
endif()

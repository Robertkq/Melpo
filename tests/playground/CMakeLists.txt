cmake_minimum_required(VERSION 3.2)
project(WiredPlayground VERSION 1.0.0)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

find_package(Wired REQUIRED)

file(GLOB_RECURSE WIRED_PLAYGROUND_SOURCES src/*.cpp)

add_executable(wired_playground ${WIRED_PLAYGROUND_SOURCES})
target_link_libraries(wired_playground PRIVATE Wired)

target_include_directories(wired_playground PRIVATE include)
add_compile_definitions(_WIN32_WINNT=0x0A00)

set_target_properties(wired_playground PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY_DEBUG ${CMAKE_BINARY_DIR}
    RUNTIME_OUTPUT_DIRECTORY_RELEASE ${CMAKE_BINARY_DIR}
)

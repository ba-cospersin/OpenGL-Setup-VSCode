# Specify the minimum required version of CMake
cmake_minimum_required(VERSION 3.10)

# Define the project name
project(ProyekOpenGL)

# Tell the compiler where to find the header (include) files
include_directories("${CMAKE_SOURCE_DIR}/dependencies/include")

# Combine your main source file and glad.c into a single executable target
add_executable(name_executable
    test-glad.cpp # Adjust the filename and the executable name
    "${CMAKE_SOURCE_DIR}/dependencies/src/glad.c"
)

# Specify the directory where the required library files are located
target_link_directories(name_executable PRIVATE "${CMAKE_SOURCE_DIR}/dependencies/lib")

# Link the essential external libraries and Windows core graphics subsystems
target_link_libraries(name_executable glfw3 opengl32 gdi32)

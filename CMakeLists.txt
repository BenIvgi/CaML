cmake_minimum_required(VERSION 3.16)
project(CaML C)

# Set C standard and build options
set(CMAKE_C_STANDARD 11)
set(CMAKE_C_STANDARD_REQUIRED ON)
set(CMAKE_C_EXTENSIONS OFF)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# Enable folders in IDEs like Visual Studio
set_property(GLOBAL PROPERTY USE_FOLDERS ON)

# Define source structure
add_subdirectory(src)

# Optional: Add testing framework later
# enable_testing()
# add_subdirectory(tests)

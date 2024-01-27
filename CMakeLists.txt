# suppress warnings
cmake_minimum_required(VERSION 3.21)

# project name
project(cmake_relearn)

# use c++ 17 standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# any flags that shoul be passed to the compiler
# 1. -Wall: enable all warnings
# 2. -Wextra: enable extra warnings
# 3. -Werror: treat warnings as errors
# 4. -Wpedantic: enable pedantic warnings
set(CMAKE_CXX_FLAGS "-Wall -Wextra -Werror -Wpedantic")

# specify the non-header source files that should be compiled
file(GLOB CPP_SOURCES
  # i.e. `src/main.cpp`, but not `src/otherdir/somefile.cpp`
  "${PROJECT_SOURCE_DIR}/src/*.cpp"
)

# specify the header files that should be included
include_directories(
  "${PROJECT_SOURCE_DIR}/src"
  "${PROJECT_SOURCE_DIR}/include"
)

# name the executable to be created and the source files to use
add_executable(main ${CPP_SOURCES})

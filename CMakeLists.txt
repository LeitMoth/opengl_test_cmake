cmake_minimum_required(VERSION 3.14)

project(opengl_test LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)

# Get glad
# Modified version of: https://github.com/Dav1dde/glad/issues/174#issuecomment-425663864
add_subdirectory(extern)

include_directories(${OPENGL_INCLUDE_DIR})

add_executable(opengl_test main.cc)
target_link_libraries(opengl_test
    PUBLIC
    ${OPENGL_gl_LIBRARY} glfw glad glm
    #optional?
    PRIVATE
    ${CMAKE_DL_LIBS})

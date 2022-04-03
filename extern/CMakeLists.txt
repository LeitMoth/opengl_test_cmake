cmake_minimum_required(VERSION 3.14 FATAL_ERROR)

include(FetchContent)

# Multi-Language Vulkan/GL/GLES/EGL/GLX/WGL Loader-Generator based on
# the official specs. http://glad.dav1d.de/
FetchContent_Declare(
    extern_glad
    GIT_REPOSITORY https://github.com/Dav1dde/glad.git
)
FetchContent_Declare(
    extern_glm
    GIT_REPOSITORY https://github.com/g-truc/glm.git
)

## Original code I copied, ended up not being necissary, it works without GLAD_ISNTALL enabled?
## honestly that last bit is slightly concerning, but I'll go with this until it breaks
#FetchContent_GetProperties(extern_glad)
#if(NOT extern_glad_POPULATED)
#    FetchContent_Populate(extern_glad)

#    set(GLAD_INSTALL ON)
#    add_subdirectory(
#        ${extern_glad_SOURCE_DIR}
#        ${extern_glad_BINARY_DIR}
#        #optional?
#        EXCLUDE_FROM_ALL
#    )
#endif()

FetchContent_MakeAvailable(extern_glm extern_glad)

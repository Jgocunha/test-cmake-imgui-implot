cmake_minimum_required (VERSION 3.8)

# setup imgui library
set(IMGUI_HEADERS
    ./imgui/imconfig.h
    ./imgui/imgui_internal.h
    ./imgui/imgui.h
    ./imgui/imstb_rectpack.h
    ./imgui/imstb_textedit.h
    ./imgui/imstb_truetype.h    
    ./imgui/backends/imgui_impl_win32.h
    ./imgui/backends/imgui_impl_opengl3.h
    ./imgui/backends/imgui_impl_opengl3_loader.h
    ./imgui/misc/cpp/imgui_stdlib.h
)

set(IMGUI_SRC
    ./imgui/imgui_demo.cpp
    ./imgui/imgui_draw.cpp
    ./imgui/imgui_tables.cpp
    ./imgui/imgui_widgets.cpp
    ./imgui/imgui.cpp
    ./imgui/backends/imgui_impl_win32.cpp
    ./imgui/backends/imgui_impl_opengl3.cpp
    ./imgui/misc/cpp/imgui_stdlib.cpp
)

find_package(OpenGL REQUIRED)

add_library(imgui ${IMGUI_HEADERS} ${IMGUI_SRC})

target_link_libraries(imgui PUBLIC OpenGL::GL)
target_compile_definitions(imgui PRIVATE IMGUI_DLL_EXPORT)

include_directories(./imgui/ ./imgui/examples ./imgui/examples/libs/gl3w ./imgui/backends ./imgui/misc/cpp)

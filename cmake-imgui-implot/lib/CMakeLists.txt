cmake_minimum_required (VERSION 3.8)


###############################################################################
# IMGUI
###############################################################################

set(IMGUI_HEADERS
    ./imgui/imconfig.h
    ./imgui/imgui_internal.h
    ./imgui/imgui.h
    ./imgui/imstb_rectpack.h
    ./imgui/imstb_textedit.h
    ./imgui/imstb_truetype.h    
    ./imgui/backends/imgui_impl_glfw.h
    ./imgui/backends/imgui_impl_opengl3.h
    ./imgui/backends/imgui_impl_opengl3_loader.h
    ./imgui/misc/cpp/imgui_stdlib.h
)

#message(PROJECT_SOURCE_DIR=${PROJECT_SOURCE_DIR}/lib)
#message(IMGUI_HEADERS=${IMGUI_HEADERS})

set(IMGUI_SRC
    ./imgui/imgui_demo.cpp
    ./imgui/imgui_draw.cpp
    ./imgui/imgui_tables.cpp
    ./imgui/imgui_widgets.cpp
    ./imgui/imgui.cpp
    ./imgui/backends/imgui_impl_glfw.cpp
    ./imgui/backends/imgui_impl_opengl3.cpp
    ./imgui/misc/cpp/imgui_stdlib.cpp
)


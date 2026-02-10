cmake_minimum_required(VERSION 4.1)
set(CMAKE_CXX_STANDARD 20)

set(INE_MAIN ${CMAKE_CURRENT_SOURCE_DIR})
set(INE_UTILS ${CMAKE_CURRENT_SOURCE_DIR}/utilities)
set(INE_EXT ${CMAKE_CURRENT_SOURCE_DIR}/external)
set(INE_INC_DIRS
        ${INE_MAIN}
        ${INE_UTILS}
        ${INE_EXT}
CACHE PATH "imgui-node-editor include dirs")

project(imgui-node-editor)

include_directories(BEFORE
        /
        utilities/
        external/
        ${ImGUI_SOURCE_DIR}
)



add_library(imgui-node-editor STATIC
        crude_json.cpp
        crude_json.h
        imgui_bezier_math.h
        imgui_bezier_math.inl
        imgui_canvas.cpp
        imgui_canvas.h
        imgui_extra_math.h
        imgui_extra_math.inl
        imgui_node_editor.cpp
        imgui_node_editor.h
        imgui_node_editor_api.cpp
        imgui_node_editor_internal.h
        imgui_node_editor_internal.inl
        utilities/builders.cpp
        utilities/builders.h
        utilities/drawing.cpp
        utilities/drawing.h
        utilities/widgets.cpp
        utilities/widgets.h
)

set_property(TARGET imgui-node-editor PROPERTY

        MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:Debug>")




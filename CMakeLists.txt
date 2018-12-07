cmake_minimum_required(VERSION 3.5)
project(imgui)

add_library(imgui
            imgui.h
            imgui.cpp
            imconfig.h
            imgui_demo.cpp
            imgui_draw.cpp
            imgui_internal.h
            imgui_widgets.cpp
            imstb_rectpack.h
            imstb_textedit.h
            imstb_truetype.h
            gl3w/include/GL/gl3w.h
            gl3w/include/GL/glcorearb.h
            gl3w/gl3w.c
            examples/imgui_impl_glfw.h
            examples/imgui_impl_glfw.cpp
            examples/imgui_impl_opengl2.h
            examples/imgui_impl_opengl2.cpp)

find_package(OpenGL REQUIRED)

target_include_directories(imgui PUBLIC
                           ${CMAKE_CURRENT_SOURCE_DIR}
                           ${CMAKE_CURRENT_SOURCE_DIR}/gl3w/include
                           ${CMAKE_CURRENT_SOURCE_DIR}/examples)
target_link_libraries(imgui PUBLIC glfw ${OPENGL_LIBRARIES})

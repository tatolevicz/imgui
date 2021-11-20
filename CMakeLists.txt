set(IMGUI_SOURCE
        imgui.h
        imstb_rectpack.h
        imstb_textedit.h
        imstb_truetype.h
        imgui_internal.h
        imconfig.h
        misc/cpp/imgui_stdlib.h
        backends/imgui_impl_glfw.h
        backends/imgui_impl_opengl3.h
        )

set(IMGUI_HEADER
        imgui.cpp
        misc/cpp/imgui_stdlib.cpp
        imgui_draw.cpp
        imgui_widgets.cpp
        imgui_tables.cpp
        imgui_demo.cpp
        backends/imgui_impl_glfw.cpp
        backends/imgui_impl_opengl3.cpp
        )

add_library(docking_imgui STATIC ${IMGUI_SOURCE} ${IMGUI_HEADER})

target_include_directories(docking_imgui
        PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}
        PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/misc/cpp
        PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/backends
        )

target_link_libraries(docking_imgui glfw glad)
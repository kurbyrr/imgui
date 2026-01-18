add_library(imgui STATIC
        imgui.cpp
        imgui_demo.cpp
        imgui_draw.cpp
        imgui_tables.cpp
        imgui_widgets.cpp
        backends/imgui_impl_glfw.cpp
        backends/imgui_impl_vulkan.cpp
)

find_package(Vulkan REQUIRED)
target_link_libraries(imgui PUBLIC glfw Vulkan::Vulkan)
target_include_directories(imgui PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}")
target_compile_definitions(imgui PRIVATE IMGUI_IMPL_GLFW_DISABLE_X11)

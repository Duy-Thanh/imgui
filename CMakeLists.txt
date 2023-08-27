### DEAR IMGUI ###

# Add Dear ImGui source files to your project
set(IMGUI_SOURCES
    imgui.cpp
    imgui_demo.cpp
    imgui_draw.cpp
    imgui_widgets.cpp
    imgui_tables.cpp
    backends/imgui_impl_glfw.cpp
    backends/imgui_impl_glut.cpp
    backends/imgui_impl_opengl2.cpp
    backends/imgui_impl_opengl3.cpp
    misc/cpp/imgui_stdlib.cpp
    misc/fonts/binary_to_compressed_c.cpp
)

# Create an ImGui library target
add_library(imgui STATIC ${IMGUI_SOURCES})

# Set include directories for ImGui
target_include_directories(imgui PUBLIC
    ...
    ..
    # ../allegro5/include/
    ../glm-0.9.7.1/glm/
    ../glew-2.2.0/include/
    ../glfw-3.3.8/include/
    .
)

# Link ImGui to other libraries as needed
target_link_libraries(imgui PUBLIC 
    ${OPENGL_LIBRARY}
    # allegro
    # allegro_main
    # allegro_acodec
    # allegro_audio
    # allegro_color
    # allegro_dialog
    # allegro_font
    # allegro_image
    # allegro_memfile
    # allegro_primitives
    # allegro_ttf
)

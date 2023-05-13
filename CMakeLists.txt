cmake_minimum_required (VERSION 3.2)
project ("PBR-Viewer")

set (CMAKE_CXX_STANDARD 20)
set (CMAKE_EXPORT_COMPILE_COMMANDS)
set (EXECUTABLE_OUTPUT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/exec-dir)

# Dependence
add_subdirectory ("ext")

# Sources
aux_source_directory (src SRC_FILES)
add_executable (
    "PBR-Viewer"
    main.cpp ${SRC_FILES}
    ${PBRV_EXT_GLAD_SRC_DIR}
)

# Headers
target_include_directories (
    "PBR-Viewer" PUBLIC
    include/
    ${PBRV_EXT_GLAD_INC_DIR}
    ${PBRV_EXT_GLFW_INC_DIR}
    ${PBRV_EXT_GLM_INC_DIR}
)

# Libraries
if (UNIX)
    target_link_libraries (
        "PBR-Viewer"
        glfw GL X11 Xrandr Xi
    )

elseif (WIN32)
    target_link_libraries(
        "PBR-Viewer"
        glfw opengl32
    )
    
endif ()
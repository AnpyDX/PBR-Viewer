# PBR-Viewer
# - Ext (3rd Party)

set (PBRV_EXT_DIR ${CMAKE_CURRENT_SOURCE_DIR})

# --> GLAD
set (PBRV_EXT_GLAD_INC_DIR ${PBRV_EXT_DIR}/glad/include CACHE INTERNAL "")
set (PBRV_EXT_GLAD_SRC_DIR ${PBRV_EXT_DIR}/glad/src/glad.c CACHE INTERNAL "")

# --> GLFW
add_subdirectory (glfw)
option (GLFW_BUILD_EXAMPLES OFF)
option (GLFW_BUILD_TESTS OFF)
option (GLFW_BUILD_DOCS OFF)
option (GLFW_INSTALL OFF)
option (GLFW_VULKAN_STATIC OFF)
set (PBRV_EXT_GLFW_INC_DIR ${PBRV_EXT_DIR}/glfw/include CACHE INTERNAL "")

# --> GLM
set (PBRV_EXT_GLM_INC_DIR ${PBRV_EXT_DIR}/glm/include CACHE INTERNAL "")
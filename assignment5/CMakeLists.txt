cmake_minimum_required(VERSION 3.5...3.28)
include(FetchContent)
project(assignment5)

set(CMAKE_CXX_STANDARD 14)

FetchContent_Declare(
    libigl
    GIT_REPOSITORY https://github.com/libigl/libigl.git
    GIT_TAG v2.4.0
)
FetchContent_MakeAvailable(libigl)
igl_include(glfw)
igl_include(imgui)

# Add your project files
FILE(GLOB SRCFILES src/*.cpp)
FILE(GLOB SRCFILES ${CMAKE_CURRENT_LIST_DIR}/src/*.cpp)
add_executable(${PROJECT_NAME} ${SRCFILES})
target_link_libraries(${PROJECT_NAME} igl::core igl::imgui igl::glfw)

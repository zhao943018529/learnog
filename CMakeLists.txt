cmake_minimum_required(VERSION 3.0.0)
project(learnog VERSION 0.1.0)

include(CTest)
include_directories(/opt/homebrew/Cellar/glfw/3.3.7/include)
link_directories(/opt/homebrew/Cellar/glfw/3.3.7/lib)
include_directories(/opt/homebrew/Cellar/glad/include)
include_directories(${PROJECT_SOURCE_DIR} include)
include_directories(${PROJECT_SOURCE_DIR} glad.c)
enable_testing()

add_executable(${PROJECT_NAME} main.cpp glad.c)
# add_executable(${PROJECT_NAME} Shader.cpp)

target_link_libraries(${PROJECT_NAME} libglfw.dylib)
# target_link_libraries(learnog "-framework OpenGL")
set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)

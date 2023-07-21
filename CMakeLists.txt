cmake_minimum_required(VERSION 3.10)

project(LearnOpenGL)
set(CMAKE_CXX_STANDARD 14)

find_package(OpenGL REQUIRED)
SET(GLFW_DIR  ${CMAKE_CURRENT_SOURCE_DIR}/third-party/glfw/include)
SET(GLFW_LIB  ${CMAKE_CURRENT_SOURCE_DIR}/third-party/glfw/lib/libglfw.3.dylib)
SET(GLEW_DIR  ${CMAKE_CURRENT_SOURCE_DIR}/third-party/glew/include)
SET(GLEW_LIB  ${CMAKE_CURRENT_SOURCE_DIR}/third-party/glew/lib/libGLEW.a)

add_executable(${PROJECT_NAME} ${CMAKE_CURRENT_SOURCE_DIR}/main.cpp)
include_directories(
    ${CMAKE_CURRENT_SOURCE_DIR}/third-party/glfw/include
    ${GLFW_DIR}
    ${GLEW_DIR}
    ${OPENGL_INCLUDE_DIR}
)
 
target_link_libraries(${PROJECT_NAME} 
    # MacOS下使用glfw 使用动态库会更方便一点
    ${GLFW_LIB}
    ${GLEW_LIB}
    ${OPENGL_LIBRARIES}
)

MESSAGE(GLFW_DIR -- ${CMAKE_CURRENT_SOURCE_DIR}/third-party/glfw/include)
MESSAGE(GLFW_LIB -- ${CMAKE_CURRENT_SOURCE_DIR}/third-party/glfw/lib/libglfw3.a)
MESSAGE(OPENGL_INCLUDE_DIR -- ${OPENGL_INCLUDE_DIR})
MESSAGE(OPENGL_LIBRARIES -- ${OPENGL_LIBRARIES})
MESSAGE(OPENGL_DEFINITIONS -- ${OPENGL_DEFINITIONS})
MESSAGE(OPENGL_VERSION -- ${OPENGL_VERSION})
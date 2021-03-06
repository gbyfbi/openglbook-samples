cmake_minimum_required(VERSION 2.6.0)

project(chapter-3)

find_package(OpenGL REQUIRED)
find_package(GLEW REQUIRED)
find_package(GLUT REQUIRED)

message(STATUS OPENGL_INCLUDE_DIRS: "${OpenGL_INCLUDE_DIRS}")
message(STATUS GLUT_INCLUDE_DIRS: "${GLUT_INCLUDE_DIRS}")
message(STATUS GLEW_INCLUDE_DIRS: "${GLEW_INCLUDE_DIRS}")

message(STATUS OPENGL_LIBRARIES: "${OPENGL_LIBRARIES}")
message(STATUS GLUT_LIBRARIES: "${GLUT_LIBRARIES}")
message(STATUS GLEW_LIBRARIES: "${GLEW_LIBRARIES}")

message(STATUS OPENGL_FOUND: ${OPENGL_FOUND})
message(STATUS GLUT_FOUND: ${GLUT_FOUND})

include_directories(${OPENGL_INCLUDE_DIRS} ${GLUT_INCLUDE_DIRS} ${GLEW_INCLUDE_DIRS})

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_CURRENT_SOURCE_DIR}")
set(CMAKE_CXX_FLAGS "-O3 -msse2 -msse3 -Wall -std=c++11")

add_executable(chapter.3.0.1 chapter.3.0.1.c)
add_executable(chapter.3.0.2 chapter.3.0.2.c)
add_executable(chapter.3.1 chapter.3.1.c)
add_executable(chapter.3.2 chapter.3.2.c)

target_link_libraries(chapter.3.0.1 ${GLUT_LIBRARIES} ${OPENGL_LIBRARIES} ${GLEW_LIBRARIES})
target_link_libraries(chapter.3.0.2 ${GLUT_LIBRARIES} ${OPENGL_LIBRARIES} ${GLEW_LIBRARIES})
target_link_libraries(chapter.3.1 ${GLUT_LIBRARIES} ${OPENGL_LIBRARIES} ${GLEW_LIBRARIES})
target_link_libraries(chapter.3.2 ${GLUT_LIBRARIES} ${OPENGL_LIBRARIES} ${GLEW_LIBRARIES})

set(CMAKE_VERBOSE_MAKEFILE on)

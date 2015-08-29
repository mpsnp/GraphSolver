project(GraphSolver)

cmake_minimum_required(VERSION 2.8)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake")

find_package(OpenCV)

set(MC_SOURCES
	GraphSolver.cpp
)

set(MC_HEADERS
	GraphSolver.h
)

INCLUDE_DIRECTORIES(
	${OpenCV_INCLUDE_DIRS}
)

add_library( graph-solver STATIC 
	${MC_SOURCES}
	${MC_HEADERS}
)

target_link_libraries( graph-solver 
	${OpenCV_LIBS}
)

target_compile_features(graph-solver PRIVATE cxx_range_for)
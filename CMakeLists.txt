cmake_minimum_required (VERSION 2.6)
project (GPSEE-ami)
set (VERSION_MAJOR 0)
set (VERSION_MINOR 1)

configure_file (
	"${PROJECT_SOURCE_DIR}/Config.h.in"
	"${PROJECT_BINARY_DIR}/Config.h"
)

include_directories("${PROJECT_BINARY_DIR}")
include_directories("${PROJECT_SOURCE_DIR}/include")

find_library(JSAPI js)

set(CMAKE_C_FLAGS "-g -Wall")

add_executable(unit 
	unit/main.c
)
target_link_libraries(unit 
	${JSAPI} 
)



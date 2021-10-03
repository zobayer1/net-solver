cmake_minimum_required(VERSION 3.20)

project(netgame-solver VERSION 0.0.1 DESCRIPTION "Netgame Solver" LANGUAGES CXX)

enable_testing()

add_subdirectory(src)
add_subdirectory(test)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
set(CMAKE_INSTALL_PREFIX ${PROJECT_SOURCE_DIR})

set(NGSOLVER_INSTALL_INCLUDE_DIR ${PROJECT_SOURCE_DIR}/include)
set(NGSOLVER_INSTALL_BIN_DIR ${PROJECT_SOURCE_DIR}/bin)
set(NGSOLVER_INSTALL_LIB_DIR ${PROJECT_SOURCE_DIR}/lib)
set(SOLVER_HEADERS_DIR ${PROJECT_SOURCE_DIR}/src/solver)
set(IMGPROC_HEADERS_DIR ${PROJECT_SOURCE_DIR}/src/imgproc)

include_directories(${NGSOLVER_INSTALL_INCLUDE_DIR})
include_directories(${SOLVER_HEADERS_DIR})
include_directories(${IMGPROC_HEADERS_DIR})

configure_file(${PROJECT_SOURCE_DIR}/src/version.h.in ${PROJECT_BINARY_DIR}/include/version.h)
install(FILES ${PROJECT_BINARY_DIR}/include/version.h DESTINATION ${NGSOLVER_INSTALL_INCLUDE_DIR})
target_include_directories(ngsolver PUBLIC ${PROJECT_BINARY_DIR})

cmake_minimum_required(VERSION 3.20)

project(ngsolver CXX)

add_subdirectory(solver)
add_subdirectory(imgproc)
set(SOURCE_FILES main.cpp)

add_executable(ngsolver ${SOURCE_FILES})
target_link_libraries(ngsolver solver)
target_link_libraries(ngsolver imgproc)
install(TARGETS ngsolver DESTINATION ${NGSOLVER_INSTALL_BIN_DIR})

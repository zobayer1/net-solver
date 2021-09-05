cmake_minimum_required(VERSION 3.20)

project(imgproc CXX)

set(SOURCE_FILES process.h process.cpp)

add_library(imgproc SHARED STATIC ${SOURCE_FILES})

find_package(OpenCV 4.5.0 REQUIRED)
if (OpenCV_FOUND)
    message(STATUS "OpenCV ${OpenCV_VERSION} found")
    target_link_libraries(imgproc ${OpenCV_LIBS})
    include_directories(${OpenCV_INCLUDE_DIRS})
else()
    message(FATAL_ERROR "Could not locate OpenCV libraries")
endif()

install(TARGETS imgproc DESTINATION ${NGSOLVER_INSTALL_LIB_DIR})
install(FILES process.h DESTINATION include ${NGSOLVER_INSTALL_INCLUDE_DIR})

project(solver CXX)

set(SOURCE_FILES algorithm.h algorithm.cpp)

add_library(solver SHARED STATIC ${SOURCE_FILES})

install(TARGETS solver DESTINATION ${NGSOLVER_INSTALL_LIB_DIR})
install(FILES algorithm.h DESTINATION include ${NGSOLVER_INSTALL_INCLUDE_DIR})

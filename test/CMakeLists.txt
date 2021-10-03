project(ngsolvertst CXX)

add_subdirectory(lib/googletest)
set(TEST_SOURCE_FILES version_test.cpp)

add_executable(ngsolvertst ${TEST_SOURCE_FILES})
target_link_libraries(ngsolvertst gtest_main)

include(GoogleTest)
gtest_discover_tests(ngsolvertst)

cmake_minimum_required(VERSION 2.6)
 
# Locate GTest
find_package(GTest REQUIRED)
include_directories(${GTEST_INCLUDE_DIRS} ../)
  
# Link runTests with what we want to test and the GTest and pthread library
add_executable(runTests ../romberg_integrator.cpp ./romberg_integrator.t.cpp ../cumulative_normal.cpp ./cumulative_normal.t.cpp ../root_finder.cpp ./root_finder.t.cpp)
target_link_libraries(runTests ${GTEST_LIBRARIES} ${GTEST_MAIN_LIBRARY} pthread)

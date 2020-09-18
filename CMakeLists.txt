cmake_minimum_required (VERSION 3.10.0)

project(
  LambertW
  VERSION 3.6.7
  LANGUAGES CXX
)

# std >= 14 for conditional_t
# std >= 17 for inline variables
set(CMAKE_CXX_STANDARD 17)

add_library(LambertW LambertW.cc FukushimaLambertW.cc)
target_include_directories(LambertW PUBLIC .)

add_executable(lambertw lambertw.cxx)
target_link_libraries(lambertw LambertW)

add_executable(test_accuracy test_accuracy.cxx)
target_link_libraries(test_accuracy LambertW)

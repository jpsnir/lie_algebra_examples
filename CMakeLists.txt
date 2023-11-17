cmake_minimum_required(VERSION 3.10)
project(lie_algebra_examples)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
find_package(fmt REQUIRED)
find_package(Eigen3 REQUIRED)
find_package(Sophus)
find_package(manif)
include_directories(
    ${fmt_INCLUDE_DIRS}
    ${Sophus_INCLUDE_DIRS}
    ${manif_INCLUDE_DIRS}
    ${Eigen_INCLUDE_DIRS}
)
if(${fmt_FOUND})
    message(STATUS "fmt found")
endif()
if(${manif_FOUND})
    message(STATUS "manif found")
endif()
if(${Sophus_FOUND})
    message(STATUS "Sophus found")
endif()
add_executable(hello_lie ./src/hello_manif.cpp)
target_link_libraries(hello_lie Eigen3::Eigen sophus manif)

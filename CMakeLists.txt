cmake_minimum_required(VERSION 3.10)
project(MeanAndCovariance)

set(CMAKE_CXX_STANDARD 14)

include(deps/eigen.cmake)

if (UNIX)
    # Silence warnings in Eigen
    add_compile_options(-Wno-deprecated-register)
endif()



add_executable(MeanAndCovariance
    ${CMAKE_SOURCE_DIR}/src/main.cpp
    ${CMAKE_SOURCE_DIR}/src/ukf.h
    ${CMAKE_SOURCE_DIR}/src/ukf.cpp
)

target_link_libraries(MeanAndCovariance Eigen)

cmake_minimum_required(VERSION 2.6 FATAL_ERROR)
project(spline_fitting)

# Eigen
set(EIGEN_DIR  ${CMAKE_CURRENT_SOURCE_DIR}/../external/eigen-3.4.0)
include_directories(${EIGEN_DIR})

# nanoflann
set(NANOFLANN_DIR  ${CMAKE_CURRENT_SOURCE_DIR}/../external/nanoflann)
include_directories(${NANOFLANN_DIR})

#include directories
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/core)



set(incs    
			core/cubic_b_spline.h
			core/open_cubic_b_spline.h
			core/spline_curve_fitting.h			
            )
			
set(srcs    core/cubic_b_spline.cpp
			core/open_cubic_b_spline.cpp
            core/spline_curve_fitting.cpp
			)
			

add_executable(spline_fitting_test ${incs} ${srcs} read_write_asc.h  read_write_asc.cpp main.cpp )
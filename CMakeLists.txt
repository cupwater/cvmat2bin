# MatlabIO CMakeLists.txt
cmake_minimum_required(VERSION 2.8)
project(cvmatio)


# find the dependencies
find_package(Boost REQUIRED)
find_package(OpenCV REQUIRED)
include(FindZLIB)

# include the dependencies
include_directories(SYSTEM ${OPENCV_INCLUDE_DIRS}
                           ${Boost_INCLUDE_DIRS}
                           ${ZLIB_INCLUDE_DIR})

include_directories("include")

SET(CMAKE_BUILD_TYPE "Debug")  
SET(CMAKE_CXX_FLAGS_DEBUG "$ENV{CXXFLAGS} -O0 -Wall -g2 -ggdb -std=c++11")  
SET(CMAKE_CXX_FLAGS_RELEASE "$ENV{CXXFLAGS} -O3 -Wall")  


set(SRC_FILES MatlabIO.cpp main.cpp)
add_executable(${PROJECT_NAME} ${SRC_FILES})

target_link_libraries(${PROJECT_NAME}   ${Boost_LIBRARIES} 
                                        ${OpenCV_LIBS} 
                                        ${ZLIB_LIBRARIES}
)
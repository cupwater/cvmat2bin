# build the project


set(BUILD_EXECUTABLE True)
#if(BUILD_EXECUTABLE)
set(SRC_FILES MatlabIO.cpp main.cpp)
add_executable(${PROJECT_NAME} ${SRC_FILES})

#link
target_link_libraries(${PROJECT_NAME}   ${Boost_LIBRARIES} 
                                        ${OpenCV_LIBS} 
                                        ${ZLIB_LIBRARIES}
)


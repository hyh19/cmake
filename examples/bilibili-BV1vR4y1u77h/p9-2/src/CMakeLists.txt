INCLUDE_DIRECTORIES(/usr/local/include/hello)

ADD_EXECUTABLE(main main.cpp)

TARGET_LINK_LIBRARIES(main libhello.a)
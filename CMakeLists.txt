cmake_minimum_required(VERSION 2.8)

include_directories (./) 

set (SRC
    ev_stub.cpp
    )

add_library (ev ${SRC})

if (WIN32)
set_property (
    TARGET libev
    PROPERTY COMPILE_DEFINITIONS _CRT_SECURE_NO_WARNINGS
    )
endif (WIN32)


install (TARGETS ev ARCHIVE DESTINATION lib)
install (FILES ev.h DESTINATION include)

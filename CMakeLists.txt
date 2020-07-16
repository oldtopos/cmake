cmake_minimum_required(VERSION 3.12.2)

project (addnum)

add_library(addnum STATIC src/add_num.cpp)
target_include_directories( addnum 
    PUBLIC
        "${CMAKE_CURRENT_SOURCE_DIR}/include"
)

add_executable(addnumapp src/main.cpp)
target_link_libraries(addnumapp addnum)

install(TARGETS addnumapp
    COMPONENT linapp
    RUNTIME DESTINATION "/home/"
    LIBRARY DESTINATION "/home/"
    DESTINATION "/home/"
)

SET(CPACK_GENERATOR "DEB")
SET(CPACK_DEBIAN_PACKAGE_MAINTAINER "Samsung ATG") #required
SET(CPACK_PACKAGE_VERSION_MAJOR 1)
SET(CPACK_PACKAGE_VERSION_MINOR 2)
SET(CPACK_PACKAGE_VERSION_PATCH 0)
SET(CPACK_PACKAGE_DESCRIPTION "Debian pckaging for CMake exemplar")
INCLUDE(CPack)

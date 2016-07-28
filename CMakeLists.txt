cmake_minimum_required (VERSION 2.8)
project (XZ_Utils C)

if(WIN32)

    INCLUDE_EXTERNAL_MSPROJECT(xz_utils ${CMAKE_CURRENT_SOURCE_DIR}/windows/xz_win.sln)

else(WIN32)

    include(ExternalProject)
    ExternalProject_Add(xz_utils
        SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}
        CONFIGURE_COMMAND ${CMAKE_CURRENT_SOURCE_DIR}/configure --prefix=<INSTALL_DIR>
        BUILD_COMMAND ${MAKE})

endif(WIN32)

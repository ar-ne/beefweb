include(ExternalProject)

ExternalProject_Add(
    ext_catch
    PREFIX
        ${EXTLIB_INSTALL_DIR}
    URL
        https://github.com/philsquared/Catch/releases/download/v1.9.3/catch.hpp
    URL_HASH
        SHA256=add614987e6215a2a095410765f5e5ac17f3b4f4019e9aad01e49a551b9f03ea
    DOWNLOAD_DIR
        ${EXTLIB_CACHE_DIR}/catch
    DOWNLOAD_NO_EXTRACT 1
    CONFIGURE_COMMAND ""
    BUILD_COMMAND ""
    INSTALL_COMMAND
        ${CMAKE_COMMAND} -E copy_if_different <DOWNLOADED_FILE> ${EXTLIB_INSTALL_DIR}/include/catch.hpp
    LOG_DOWNLOAD 0 LOG_UPDATE 0 LOG_CONFIGURE 0 LOG_BUILD 0 LOG_INSTALL 1
)

add_dependencies(ext_all ext_catch)

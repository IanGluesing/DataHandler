add_library(data_forwarder_library STATIC src/data_forwarder.cpp)

target_include_directories(data_forwarder_library PUBLIC
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
    $<INSTALL_INTERFACE:include>
)

target_link_libraries(
    data_forwarder_library

    libzmq
    libcppzmq
)

install(TARGETS data_forwarder_library
    EXPORT MyLibsTargets
    ARCHIVE DESTINATION lib
)

install(DIRECTORY include/ DESTINATION include)
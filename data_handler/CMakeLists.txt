add_library(data_handler STATIC src/data_handler.cpp)

target_include_directories(data_handler PUBLIC
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
    $<INSTALL_INTERFACE:include>
)

target_link_libraries(data_handler
    PUBLIC

        data_forwarder_library
)

install(TARGETS data_handler
    EXPORT MyLibsTargets
    ARCHIVE DESTINATION lib
)

install(DIRECTORY include/ DESTINATION include)

add_executable(Compressor main.cpp)
target_link_libraries(Compressor CompressorLib)

if (DYN_LIBS)
    foreach(dyn ${DYN_LIBS})
        message(*** ${dyn})
        add_custom_command(TARGET Compressor POST_BUILD
                COMMAND ${CMAKE_COMMAND} -E copy
                ${dyn}
                ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}
                )
    endforeach()
endif()

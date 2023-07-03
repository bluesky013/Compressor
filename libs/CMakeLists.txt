file(GLOB_RECURSE SRC_FILES src/*)
file(GLOB_RECURSE INC_FILES include/*)

add_library(CompressorLib STATIC
        ${SRC_FILES}
        ${INC_FILES}
)

target_link_libraries(CompressorLib
        3rdParty::cxxopts
        3rdParty::ispc_texcomp)

target_include_directories(CompressorLib PUBLIC include)


add_library(common_lib)

target_sources(common_lib PRIVATE
        src/dummy.cpp
)
target_include_directories(common_lib PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/include
)

target_compile_features(common_lib PUBLIC cxx_std_14)
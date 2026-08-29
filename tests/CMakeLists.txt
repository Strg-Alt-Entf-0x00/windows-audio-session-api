# ============================================================================
# WASAPI Tests
# ============================================================================

add_executable(test_format_converter
    test_format_converter.cpp
)

# Link against wasapi (for internal headers via relative include)
target_link_libraries(test_format_converter PRIVATE wasapi)

# Allow #include "../src/format_converter.h" to work
target_include_directories(test_format_converter PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/..
)

# Register as CTest
add_test(NAME FormatConverterTest COMMAND test_format_converter)

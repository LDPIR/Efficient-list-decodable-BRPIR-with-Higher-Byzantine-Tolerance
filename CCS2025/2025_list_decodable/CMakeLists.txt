cmake_minimum_required(VERSION 3.0.0)

project(2025_list_decodable VERSION 0.1.0)

file(GLOB SOURCES src/*.cpp)
file(GLOB HEADERS include/*.hpp)

# message("Source files: ${SOURCES}")
# message("Header files: ${HEADERS}")

add_executable(2025_list_decodable ${SOURCES} ${HEADERS})

find_library(GMP_LIB gmp)
if (GMP_LIB)
    target_link_libraries(2025_list_decodable PRIVATE ${GMP_LIB})
else()
    message(FATAL_ERROR "libgmp not found")
endif()

target_link_libraries(2025_list_decodable PRIVATE m gmp flint)


target_include_directories(2025_list_decodable PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)

target_compile_definitions(2025_list_decodable PRIVATE DATA_DIR="${DATA_DIR}")

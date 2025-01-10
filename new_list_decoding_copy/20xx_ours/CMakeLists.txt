cmake_minimum_required(VERSION 3.0.0)

project(20xx_ours VERSION 0.1.0)

file(GLOB SOURCES src/*.cpp)
file(GLOB HEADERS include/*.hpp)

# message("Source files: ${SOURCES}")
# message("Header files: ${HEADERS}")

add_executable(20xx_ours ${SOURCES} ${HEADERS})

find_library(GMP_LIB gmp)
if (GMP_LIB)
    target_link_libraries(20xx_ours PRIVATE ${GMP_LIB})
else()
    message(FATAL_ERROR "libgmp not found")
endif()

target_link_libraries(20xx_ours PRIVATE m gmp flint)


target_include_directories(20xx_ours PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)

target_compile_definitions(20xx_ours PRIVATE DATA_DIR="${DATA_DIR}")

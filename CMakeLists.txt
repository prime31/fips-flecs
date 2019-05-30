#
# project: fips-flecs
#
cmake_minimum_required(VERSION 2.8)
set(CMAKE_C_STANDARD 99)
set(CMAKE_CXX_STANDARD 11)

# include the fips main cmake file
get_filename_component(FIPS_ROOT_DIR "../fips" ABSOLUTE)
include("${FIPS_ROOT_DIR}/cmake/fips.cmake")


fips_setup(PROJECT fips-flecs)

if (FIPS_CLANG OR FIPS_GCC)
    set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wsign-compare")
endif()
if (FIPS_GCC)
    set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wsign-compare")
endif()

fips_include_directories(modules)

fips_ide_group(Modules)
fips_add_subdirectory(modules/flecs)
fips_add_subdirectory(modules/flecs-admin)

fips_finish()


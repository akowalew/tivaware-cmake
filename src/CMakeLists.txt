set(CMAKE_C_FLAGS_DEBUG "-g -Os")

# Specify compiler flags for all targets
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} \
-std=c11 \
-Wall \
-Werror \
-ffunction-sections \
-fdata-sections \
")

set(CMAKE_EXE_LINKER_FLAGS "\
-Wl,--gc-sections \
")

add_definitions(-Dgcc)

add_subdirectory(driverlib)
add_subdirectory(utils)

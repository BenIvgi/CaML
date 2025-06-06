# Gather source files
file(GLOB_RECURSE SOURCES CONFIGURE_DEPENDS
    main.c
    core/*.c
    data/*.c
    model/*.c
    train/*.c
    utils/*.c
)

file(GLOB_RECURSE HEADERS CONFIGURE_DEPENDS
    ../include/*.h
)

# Create executable
add_executable(caml ${SOURCES} ${HEADERS})

# Include directories
target_include_directories(caml PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/../include
)

# Warnings and flags
if (MSVC)
    target_compile_options(caml PRIVATE /W4)
else()
    target_compile_options(caml PRIVATE -Wall -Wextra -Wpedantic)
endif()

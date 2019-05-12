cmake_minimum_required (VERSION 2.6)
project (libmypaint)
# add_executable(Tutorial tutorial.cxx)

configure_file ("${PROJECT_SOURCE_DIR}/config.h.in"
                "${PROJECT_BINARY_DIR}/config.h" )

include_directories(${PROJECT_BINARY_DIR})

add_library(mypaint SHARED brushmodes.c
config.h
fifo.c
helpers.c
mypaint-mapping.c
mypaint.c
mypaint.h
mypaint-brush.c
mypaint-brush-settings.c
mypaint-fixed-tiled-surface.c
mypaint-rectangle.c
mypaint-surface.c
mypaint-tiled-surface.c
operationqueue.c
rng-double.c
tilemap.c
utils.c)

#target_include_directories(libmypaint SYSTEM PUBLIC mypaint-brush.h mypaint-config.h mypaint-glib-compat.h mypaint-surface.h mypaint-brush-settings.h)

message(${PROJECT_SOURCE_DIR})

target_include_directories(mypaint SYSTEM PUBLIC ${PROJECT_SOURCE_DIR})

#target_include_directories(libmypaint SYSTEM PUBLIC mypaint-config.h
#        mypaint-glib-compat.h
#        mypaint-mapping.h)
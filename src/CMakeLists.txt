if(BUILD_SHARED_LIBS)
    add_library(potential-robot SHARED "")
else()
    add_library(potential-robot STATIC "")
endif()

target_sources(potential-robot
    PRIVATE
    robot.c
    robot-helper.c
)
target_include_directories(potential-robot
    PUBLIC
    .
    ${PROJECT_SOURCE_DIR}/include
)
# set_target_properties(potential-robotStatic PROPERTIES OUTPUT_NAME potential-robot)

# add_library(potential-robot-objs OBJECT "")


# target_compile_options(potential-robot-objs
#     PRIVATE
#     $<$<CONFIG:RELEASE>:${RELEASE_COMPILE_OPTIONS}>
#     $<$<CONFIG:DEBUG>:${DEBUG_COMPILE_OPTIONS}>
# )


# # using object library for building final libs
# add_library(potential-robot STATIC $<TARGET_OBJECTS:potential-robot-objs>) 


# # build libs directly
# add_library() # make shared
# #for shared we also set link options and link libraries


# # no link options or libs for static
# add_library(target STATIC "") 
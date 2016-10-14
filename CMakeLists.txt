cmake_minimum_required(VERSION 2.8)
project(poly2tri)

file( GLOB_RECURSE sources "poly2tri/*.cc" )

add_library( ${PROJECT_NAME} SHARED ${sources} )

# Install lib
install(
    TARGETS ${PROJECT_NAME}
    LIBRARY DESTINATION lib/
)

# Install headers
install(
    DIRECTORY poly2tri/
    DESTINATION include/${PROJECT_NAME}
    FILES_MATCHING
        PATTERN "*.h*" PERMISSIONS OWNER_READ GROUP_READ WORLD_READ
        PATTERN "*.orig" EXCLUDE
        PATTERN "*.autosave" EXCLUDE
)

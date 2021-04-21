cmake_minimum_required(VERSION 3.15)

project(the-forge-starter LANGUAGES CXX)

find_package(The-Forge REQUIRED CONFIG)

# SET(
#     SRC_SOURCES
#     src/models/mkc_component.cpp
#     src/models/mkc_entity.cpp
# )
# SET(
#     SRC_HEADERS
#     # models
#     src/models/mkc_component.hpp
#     src/models/mkc_entity.hpp
#     src/models/mkc_vector3.h
#     src/models/mkc_quaternion.h
#     src/models/mkc_message.h
    
#     # features
#     src/features/mkc_entity_manager.h
#     src/features/mkc_game.h
# )
add_executable(
    ${PROJECT_NAME}
    # ${SRC_HEADERS}
)
target_sources(
    ${PROJECT_NAME} PRIVATE
    main.cpp
    # ${SRC_SOURCES}
)
set_property(GLOBAL PROPERTY USE_FOLDERS ON)
source_group(TREE ${CMAKE_CURRENT_SOURCE_DIR} FILES ${SRC_HEADERS} ${SRC_SOURCES})

target_link_libraries(
    ${PROJECT_NAME} PRIVATE
    the-forge::the-forge
)

set_target_properties(
    ${PROJECT_NAME} PROPERTIES CXX_STANDARD 11)

# required for project when using visual studio or xcode generator
set_target_properties(
    ${PROJECT_NAME} PROPERTIES
    VS_DEBUGGER_WORKING_DIRECTORY ${CMAKE_SOURCE_DIR}
    XCODE_GENERATE_SCHEME TRUE
    XCODE_SCHEME_WORKING_DIRECTORY "${CMAKE_SOURCE_DIR}")

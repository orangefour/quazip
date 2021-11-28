find_package(Qt6 COMPONENTS Core Core5Compat REQUIRED)

# Must be added to enable export macro
add_definitions(-DQUAZIP_BUILD)

file(GLOB_RECURSE SOURCES *.cpp *.c)
add_library(quazip ${SOURCES})
target_include_directories(quazip PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(quazip z Qt::Core Qt::Core5Compat)

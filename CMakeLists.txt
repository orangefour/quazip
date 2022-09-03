find_package(QT NAMES Qt6 COMPONENTS Core Core5Compat REQUIRED)
find_package(Qt6 REQUIRED COMPONENTS Core Core5Compat)

# Must be added to enable export macro
add_definitions(-DQUAZIP_BUILD)

file(GLOB_RECURSE SOURCES *.cpp *.c)
add_library(quazip ${SOURCES})
target_include_directories(quazip PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(quazip z Qt6::Core Qt6::Core5Compat)

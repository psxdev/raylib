cmake_minimum_required(VERSION 2.6)
project(skully_escape)

# Grab the screens
file(GLOB screen_sources "screens/*.c")

# Executable & linking
add_executable(${PROJECT_NAME} skully_escape.c player.c monster.c ${screen_sources})
if (NOT TARGET raylib)
  find_package(raylib 2.0 REQUIRED)
endif()
target_link_libraries(${PROJECT_NAME} raylib)

# Resources
# Copy all of the resource files to the destination
file(COPY "resources/"  DESTINATION "resources/")

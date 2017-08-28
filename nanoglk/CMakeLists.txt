# NOTE: The files gi_blorb.h, gi_dispa.h, glk.h, and glkstart.h need to be
# copied/linked from the glk directory into this directory.

cmake_minimum_required(VERSION 3.1)

find_package(SDL REQUIRED)
find_package(SDL_ttf REQUIRED)
find_package(SDL_image REQUIRED)

add_library(glk nanoglk/blorb.c nanoglk/event.c nanoglk/image.c nanoglk/sound.c
  nanoglk/unsorted.c nanoglk/wingraphics.c nanoglk/wintextgrid.c
  nanoglk/dispatch.c nanoglk/fileref.c nanoglk/main.c nanoglk/stream.c
  nanoglk/window.c nanoglk/wintextbuffer.c
  misc/conf.c misc/filesel.c misc/misc.c misc/string.c misc/ui.c
  glk/gi_blorb.c glk/gi_dispa.c
  stubs.c)

target_include_directories(glk PRIVATE ${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/glk ${SDL_INCLUDE_DIR} ${SDL_TTF_INCLUDE_DIRS} ${SDL_IMAGE_INCLUDE_DIRS})
target_link_libraries(glk ${SDL_LIBRARY} ${SDL_TTF_LIBRARIES} ${SDL_IMAGE_LIBRARIES})

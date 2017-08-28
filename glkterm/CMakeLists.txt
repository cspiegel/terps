cmake_minimum_required(VERSION 3.1)

find_package(Curses REQUIRED)

add_library(glk
  main.c gtevent.c gtfref.c gtgestal.c gtinput.c
  gtmessag.c gtmessin.c gtmisc.c gtstream.c gtstyle.c
  gtw_blnk.c gtw_buf.c gtw_grid.c gtw_pair.c gtwindow.c
  gtschan.c gtblorb.c cgunicod.c cgdate.c gi_dispa.c gi_blorb.c)

target_include_directories(glk PRIVATE ${CURSES_INCLUDE_DIR})
target_link_libraries(glk ${CURSES_LIBRARIES})

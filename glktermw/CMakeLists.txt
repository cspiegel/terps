cmake_minimum_required(VERSION 3.1)

find_package(PkgConfig REQUIRED)
pkg_check_modules(NCURSESW REQUIRED ncursesw)

add_library(glk
  main.c gtevent.c gtfref.c gtgestal.c gtinput.c
  gtmessag.c gtmessin.c gtmisc.c gtstream.c gtstyle.c
  gtw_blnk.c gtw_buf.c gtw_grid.c gtw_pair.c gtwindow.c
  gtschan.c gtblorb.c cgunicod.c cgdate.c gi_dispa.c gi_blorb.c
  gtncursesw.c)

target_include_directories(glk PRIVATE ${NCURSESW_INCLUDES})
target_link_libraries(glk ${NCURSESW_LIBRARIES})

cmake_minimum_required(VERSION 3.1)

add_library(glk
  main.c rgevent.c rgfref.c rggestal.c
  rgdata.c rgmisc.c rgstream.c rgstyle.c
  rgwin_blank.c rgwin_buf.c rgwin_grid.c rgwin_pair.c rgwin_graph.c
  rgwindow.c rgschan.c rgblorb.c
  cgunicod.c cgdate.c gi_dispa.c gi_debug.c gi_blorb.c)

target_link_libraries(glk m)

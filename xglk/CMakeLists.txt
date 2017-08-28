cmake_minimum_required(VERSION 3.1)

find_package(X11 REQUIRED)
find_package(PNG REQUIRED)
find_package(JPEG REQUIRED)

add_library(glk
  main.c xglk.c xglk_vars.c xglk_prefs.c xglk_loop.c xglk_init.c
  xglk_scrap.c xglk_msg.c xglk_key.c xglk_weggie.c xglk_pict.c
  xglk_res.c
  xg_event.c xg_window.c xg_stream.c xg_fileref.c xg_style.c xg_misc.c
  xg_gestalt.c xg_win_textbuf.c xg_win_textgrid.c xg_win_graphics.c
  xg_schan.c
  gi_dispa.c gi_blorb.c)

target_include_directories(glk PRIVATE ${X11_INCLUDE_DIR} ${PNG_INCLUDE_DIRS} ${JPEG_INCLUDE_DIR})
target_link_libraries(glk ${X11_LIBRARIES} ${PNG_LIBRARIES} ${JPEG_LIBRARIES})
add_definitions(${PNG_DEFINITIONS})

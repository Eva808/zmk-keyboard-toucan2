toucan.keymap: changed RC to RCTRL because toucan firmware has some macros for RC, keymap editor stops working

correction: changed right modifiers to left, compiled




cmakelists.txt 

  if(CONFIG_TOUCAN_STATUS_SCREEN EQUAL 2)
    zephyr_library_sources(widgets/battery_arc.c)
    zephyr_library_sources(widgets/battery_arc_peripheral.c)
    zephyr_library_sources(widgets/output_arc.c)
    zephyr_library_sources(widgets/chart.c)
  else()
    zephyr_library_sources(widgets/battery.c)
    zephyr_library_sources(widgets/battery_peripheral.c)
    zephyr_library_sources(widgets/output.c)
  endif()  


  to 


  if(CONFIG_TOUCAN_STATUS_SCREEN EQUAL 2)
    zephyr_library_sources(widgets/battery_arc.c)
    zephyr_library_sources(widgets/battery_arc_peripheral.c)
else()
    zephyr_library_sources(widgets/battery.c)
    zephyr_library_sources(widgets/battery_peripheral.c)
endif()
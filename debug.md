toucan.keymap: changed RC to RCTRL because toucan firmware has some macros for RC, keymap editor stops working

correction: changed right modifiers to left, compiled


removed nice view in build
  - board: seeeduino_xiao_ble
    shield: toucan_left rgbled_adapter nice_view_gem
    snippet: studio-rpc-usb-uart
    cmake-args: -DCONFIG_ZMK_SPLIT=y -DCONFIG_ZMK_SPLIT_ROLE_CENTRAL=n
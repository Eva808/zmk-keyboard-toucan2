toucan.keymap: changed RC to RCTRL because toucan firmware has some macros for RC, keymap editor stops working




include:
  - board: seeeduino_xiao_ble
    shield: toucan_left rgbled_adapter nice_view_gem
    snippet: studio-rpc-usb-uart
    cmake-args: -DCONFIG_ZMK_SPLIT=y -DCONFIG_ZMK_SPLIT_ROLE_CENTRAL=n
  - board: seeeduino_xiao_ble
    shield: toucan_right rgbled_adapter
    cmake-args: -DCONFIG_ZMK_SPLIT=y -DCONFIG_ZMK_SPLIT_ROLE_CENTRAL=n
  - board: seeeduino_xiao_ble
    shield: settings_reset



if SHIELD_TOUCAN_DONGLE

# Max 16 characters in keyboard name
config ZMK_KEYBOARD_NAME
    default "toucan"

config ZMK_SPLIT_ROLE_CENTRAL
    default y

config ZMK_SPLIT
    default y

# Set this to the number of peripherals your dongle will have.
# For a unibody, this would be 1. If you have left and right halves, set it to 2, etc.
config ZMK_SPLIT_BLE_CENTRAL_PERIPHERALS
    default 2

# Set this to ZMK_SPLIT_BLE_CENTRAL_PERIPHERALS + your desired number of BT profiles (default is 5)
config BT_MAX_CONN
    default 7

# Set this to the same number as BT_MAX_CONN
config BT_MAX_PAIRED
    default 7
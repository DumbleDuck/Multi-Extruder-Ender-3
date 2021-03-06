# Multi extruder setup on Ender 3

This project focuses on modifying an of the shelf 3D printer to accomodate multi extruder setup. The main board on the Ender-3 is very limited in terms of expandability and hence, needs to be swapped with a more upgradable one like the MKS Gen L or the SKR Mini E3. This project has used the MKS Gen L. 

---
### Steps: 
1. 3D printing the required additional parts: dual extruder mount, motherboard cabinet, second extruder mount and additional spool holder. 
2. Disassembling: Hotend, Motherboard tray. 
3. Uploading the Marlin firmware with required changes for multi extruder setup. 
4. Assembling the printer back. 

---
### Firmware update: 
Make the following changes to the firmware. For Marlin-bugfix-2.0.x, just replace configuration.h and configuration_adv.h with the corresponding files provided along with the code.
1. configuration.h
- #define MOTHERBOARD BOARD_MKS_GEN_L 
- uncomment #define MIXING_EXTRUDER
- #define MIXING_STEPPERS 2 
- #define MIXING_VIRTUAL_TOOLS 20
- #define E0_DRIVER_TYPE A4988
- #define E1_DRIVER_TYPE A4988
- #define INVERT_E0_DIR false  (change if direction of rotation is inverted)
- #define INVERT_E1_DIR true   (change if direction of rotation is inverted)
- Uncomment #define PID_EDIT_MENU 
- Uncomment #define REPRAP_DISCOUNT_FULL_GRAPHIC_SMART_CONTROLLER (if using stock display)

2. configuration_adv.h
- #define WATCH_TEMP_PERIOD 20  (increase and calibrate if not using a silicone sock and machine shows "HEATING FAILED")
- #define MARLIN_BRICKOUT (for fun..heh)

---
### Prints for modification:
Download and print the STL files. Assemble according to the pictures.
Note: The MKS Gen L mount is modified version of the one designed by Teaching Tech ([Youtube](https://www.youtube.com/c/TeachingTech), [Thingiverse](https://www.thingiverse.com/thing:3688967)).

**Hotend Mount Assembly**
![Hotend Mount Assembly](https://user-images.githubusercontent.com/103637312/178162715-91cc8bc4-fdec-4805-a6c3-18e71a78992e.png)


**MKS Gen L Enclosure**
![image](https://user-images.githubusercontent.com/103637312/178162741-7f1fadeb-53e4-4d76-94e4-f9656847f7b9.png)


**Modified motherboard case**

![image](https://user-images.githubusercontent.com/103637312/178162762-ed3866db-aacc-498e-8980-0b9bbc7722d2.png)



**Modified printer**

![image](https://user-images.githubusercontent.com/103637312/178162771-f75a96ff-7ce8-46f6-b277-361cb853c4af.png)



**Marlin firmware**

![image](https://user-images.githubusercontent.com/103637312/178162780-ba8be585-15b3-4e5b-a92c-6364e77b1478.png)


---

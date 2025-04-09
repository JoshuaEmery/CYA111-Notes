## Switch Boot Sequence

### Steps in the Boot Process:
1. The switch performs a **POST** (Power-On Self-Test) to check the CPU, RAM, and flash memory.
2. The switch loads the **bootloader**, a small program stored in ROM that runs after POST.
3. The switch performs low-level CPU initialization:
   - Initializes the CPU.
   - Maps physical memory.
   - Sets the CPU speed.
4. The bootloader initializes the flash file system.
5. The bootloader loads the **IOS** (Internetwork Operating System).

### Boot System Command
1. Switch attempts to boot using the boot env variable. If no variable it finds first executable it can find
2. IOS OS inits the itnerfacesing usingf the commands from startup-config called config.text in flash
3. Boot enviroment is set using boot system global config mode. IOS is in distinct folder and folder is specified. 
4. use **show boot** to see what current IOS boot is set
![alt text](<Images/Screenshot 2025-04-09 133818.png>)
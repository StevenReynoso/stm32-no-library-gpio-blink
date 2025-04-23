# STM32F4 Bare-Metal GPIO LED Blink (No HAL)

This project demonstrates how to blink an LED on the STM32F446RE microcontroller using **bare-metal C** with **direct register access**. It avoids using the STM32 HAL or CMSIS libraries, providing a minimal and educational example of low-level embedded programming.

---

##  Features

- Direct manipulation of GPIO registers without HAL or full CMSIS
- Blinks the onboard LED (LD2 on pin PA5)
- Custom `gpio_config_t` structure for pin configuration
- Handwritten startup code and interrupt vector table
- Minimal linker script and Makefile for full control over the build process


---

##  Requirements

- STM32F446RE Nucleo board (or compatible STM32 board)
- `arm-none-eabi-gcc` toolchain installed
- ST-Link utilities:
  - [`st-flash`](https://github.com/stlink-org/stlink)
  - [`st-util`](https://github.com/stlink-org/stlink)
- `make` (GNU Make)
- Optional: `arm-none-eabi-gdb` for debugging

---

##  Build and Flash

###  Build the firmware

```bash
Create the ELF, BIN files with:
- make

To Flash to the STM32 Board: 
- make flash

To Clean up any old make files incase of problems
- make clean
```

### Debugging
- Start ST-Link debug server:
- make debug

- In the GDB session:
- target extended-remote :4242_____# Connect to STM32
- monitor reset halt__________________# Reset and halt MCU for debugging
- break main_________________________# Set breakpoint (can be any symbol)
- continue____________________________# Start execution, or use 'step' for instruction-by-instruction


- You can now step through main, inspect memory/registers, or examine gpio_config_t in real-time.



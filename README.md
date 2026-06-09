# __Example: *ism6hg256x_datalog_i2c*__

How to use ISM6HG256X part API.

It illustrates it by getting the values of the accelerometer (in hg) and gyroscope (in mdps) and displaying them on a terminal.


## __1. Detailed scenario__

__Initialization phase__: At main program start, the `mx_system_init()` function is called. It initializes the peripherals, nonvolatile memory (such as flash memory, NVM, or external memories), MPU regions (if applicable), the system clock, and the SysTick.

The application executes the following __example steps__:

__Step 1__: Initializes and enables accelerometer and gyroscope features of ISM6HG256X

__Step 2__: Gets the values of the accelerometer (in hg) and gyroscope (in mdps) and displays them on a terminal

__End of example__: It is an endless example that loops infinitely on step 2

You can follow these execution steps in the terminal logs:

```text
[INFO] Step 1: ISM6HG256X sensor init completed
[INFO] Step 1: Enabling the ACC feature completed
[INFO] Step 1: Enabling the GYRO feature completed
[INFO] Step 1: Enabling the ACC High-g feature completed
[INFO] Step 2: ACC X=245 Y=130 Z=-306
[INFO] Step 2: GYR X=-45 Y=128 Z=-234
[INFO] Step 2: High-g ACC X=233 Y=128 Z=-400
```


## __2. Example configuration__

This example demonstrates the following driver:

- Part ism6hg256x.c/.h
- Part ism6hg256x/interfaces/i2c/ism6hg256x_io.c/.h


In this example, the ISM6HG256X component is configured through the I2C IO operations defined under the folder interfaces/i2c.
Once the I2C is initialized, the ISM6HG256X can be initialized too through the call of ism6hg256x_drv_init() API.
After this step, the MEMS sensor will be ready to provide the values of the accelerometer and gyroscope.


## __3. Hardware environment and setup__

### __3.1. Generic Setup__

This section describes the hardware setup principles that apply to any board.

### __3.2. Specific board setups__

<details>
<summary>On STM32C5 series.</summary>
  <summary>On board NUCLEO-C562RE.</summary>

  | Board connector | MCU pin | Signal name | ARDUINO <br> connector pin |
  | :-------------: | :-----: | :---------: | :------------------------: |
  |      CN5-10     |   PB6   |  I2C1_SCL   |  ARDUINO CONNECTOR - D15   |
  |      CN5-9      |   PB7   |  I2C1_SDA   |  ARDUINO CONNECTOR - D14   |

  - I2C ADDw = 0x6B (7-bit address).

</details>

## __4. Software setup__

To create a functional project, complete the following steps:
- Select the appropriate IoC2 file based on the combination of NUCLEO and X-NUCLEO boards. For example, use c562re_iks5a1_ism6hg256x_datalog_i2c.ioc2 for NUCLEO-C562RE and X-NUCLEO-IKS5A1.
- Open the IoC2 file with STM32CubeMX2.
- Select the preferred toolchain and generate the source code.
- Copy the main.c, main.h, example.c, and example.h files into the project folder of the generated code.
- Open the Integrated Development Environment (IDE), add the example.c and example.h files to the project.
- Add the USE_TRACE=1 to the global variables of the project.
- Compile the project.

## __5. Troubleshooting__

No specific debug tips.


## __6. See Also__

More information about ISM6HG256X part driver can be found in the [ISM6HG256X Part Driver](https://dev.st.com/stm32cube-docs/part-drivers-ism6hg256x/1.0.0/en/index.html)

More information about the STM32 ecosystem can be found in the [STM32 MCU Developer Zone](https://www.st.com/content/st_com/en/stm32-mcu-developer-zone.html).


## __7. License__

Copyright (c) 2026 STMicroelectronics.

This software is licensed under terms that can be found in the LICENSE file in the root directory
of this software component.
If no LICENSE file comes with this software, it is provided AS-IS.


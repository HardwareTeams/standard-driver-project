# Standards

## Intro

This document outlines all rules which must be followed to commit a new driver. 

## Requirements

1. The driver shall be written in c
2. The driver shall be a single header file (`.h`)  and a single source file `.c` file
3. The driver shall not have any additional dependencies
4. The driver shall provide a function to read and write to the IC through every mode of communication the IC supports (example: I2C, SPI)
    - `<device name>_<comm. protocol>_write(TODO)` for example `lis3dh_i2c_write(TODO)`
    - `<device name>_<comm. protocol>_read(TODO)`  for example `lis3dh_i2c_read(TODO)`

6. The function in (4) shall contain a commented section where the user can add device/platform specific code at time of use
7. Register names shall be defined in the header file and match datasheet name **exactly** (i.e. case sensitive). If there are spaces in the register name they shall be replaced with an underscore `_`. If the name begins with a number it shall start with r.
    | Name in Datasheet  | Name in Header |
    | ------------- | ------------- |
    | Power Management 1  | Power_Management_1  |
    | TEMP_CFG_REG  | TEMP_CFG_REG  |
    | 0 register  | r0_register  |

7. Bit field names shall be defined in the header file and match datasheet name **exactly** (i.e. case sensitive). If there are spaces in the bit field name they shall be replaced with underscore `_`

# SPIKE Prime #

This repository is a collection of useful information about the Lego SPIKE Prime hub.

## SPIKE Prime Hub Hardware ##

|                     Part | Description                                                                      |
|-------------------------:|:---------------------------------------------------------------------------------|
|                  **CPU** | STM32F413 (Architecture: ARM Cortex M4, ROM: 1M, RAM: 320k, Clock: 100MHz).      |
|     **Internal storage** | 32MB flash memory (IC: Winbond W25Q256JV).                                       |
|**Wireless connectivity** | Bluetooth supporting 1 BT and 4 BTLE connections (IC: TI CC2564C).               |
|   **Wired connectivity** | Micro USB cable.                                                                 |
|              **Display** | 25 white LEDs in a 5x5 grid and 1 RGB LED (Driver IC: TI TLC5955).               |
|        **Motor Drivers** | 6 motor outputs (Driver ICs: 3 x LB1836).                                        |
|   **Battery Management** | Lithium ion battery management (IC: MPS 2639A).                                  |

## Directory Content ##

### Filesystem ###

Dumps of the micropython filesystem on the SPIKE Prime Hub using [rshell](https://github.com/dhylands/rshell).

```shell
rshell
> connect serial /dev/ttyACM0 115200
> rsync -a /pyboard ~/spikefw
```

|                     Dump | Description                                                                      |
|-------------------------:|:---------------------------------------------------------------------------------|
| **v0.5.01.0000-42a938e** | Initial firmware (Purchased on: 28/05/2020) (Box Version: 29).                   |
| **v1.0.03.0034-c3879ab** | Updated firmware (Updated on: 02/07/2020).                                       |
| **v1.0.06.0034-b0c335b** | Updated firmware (Updated on: 17/07/2020).                                       |
| **v1.1.01.0000-6b4a939** | Updated firmware (Updated on: 01/09/2020).                                       |

### Firmware ###

Dumps of the firmware on the SPIKE Prime Hub using the micropython REPL.

```python
import firmware
firmware.flash_read(BYTE_NUMBER)
```

|                     Dump | Description                                                                      |
|-------------------------:|:---------------------------------------------------------------------------------|
| **v0.5.01.0000-42a938e** | *MISSING* Initial firmware (Purchased on: 28/05/2020) (Box Version: 29).         |
| **v1.0.03.0034-c3879ab** | Updated firmware (Updated on: 02/07/2020).                                       |
| **v1.0.06.0034-b0c335b** | Updated firmware (Updated on: 17/07/2020).                                       |
| **v1.1.01.0000-6b4a939** | Updated firmware (Updated on: 01/09/2020).                                       |

### Simulator ###

A recreation of the spike prime hardware using python to allow testing and debugging python scripts on a PC.

The aim is to create a script to dump the functions of the real hardware and then mock them to allow local development.

### Specifications ###

The Lego specification pdfs for the electrical parts of the SPIKE Prime kit.

|                     File | Description                                                                      |
|-------------------------:|:---------------------------------------------------------------------------------|
|            **stm32f413** | The microprocessor inside the hub.                                                                    |
|      **spike-prime-hub** | The main hub.                                                                    |
|  **spike-prime-battery** | Rechargeable lithium ion battery pack for the hub, capacity 2100 mAH.            |
| **medium-angular-motor** | Medium motor with integrated absolute orientation sensor, accuracy +- 3 degrees. |
|  **large-angular-motor** | Large motor with integrated absolute orientation sensor, accuracy +- 3 degrees.  |
|         **force-sensor** | Measures touch, tap, and force up to 10N (About 1Kg) at an accuracy of 0.65N.    |
|         **depth-sensor** | Measures depth to 2m (fast to 30cm) with 1mm resolution. Has 4 white LED outputs.|
|        **colour-sensor** | Measures 8 colours, reflectivity, and ambient light. Has 3 white LED outputs.    |


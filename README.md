# LabSheet-01

โค้ด
```
#include <stdio.h>
#include <stdbool.h>
#include <unistd.h>
#include "driver/gpio.h"                        // เพื่อการใช้งาน digital output (GPIO)

void app_main(void)
{
    gpio_reset_pin(22);                         // รีเซ็ตสถานะของขาหมายเลข 22
    gpio_set_direction(22, GPIO_MODE_OUTPUT);   // กำหนดให้ขาหมายเลข 22 เป็น digital output

    while (true)                                // while (true) = วนรอบไม่มีที่สิ้นสุด
    {
        gpio_set_level(22, 1);                  // สั่งให้ LED ติด
        sleep(1);                               // หน่วงเวลา 1 วินาที
        gpio_set_level(22, 0);                  // สั่งให้ LED ดับ
        sleep(1);                               // หน่วงเวลา 1 วินาที
    }
}
```
![Screenshot 2023-11-09 153131](https://github.com/CHAIYAPRUK/LabSheet-01/assets/115066395/ee1d66bf-209d-4fea-bc87-3923f6a44664)


```
â†�[0;33m--- idf_monitor on \\.\COM3 115200 ---â†�[0m
--- Quit: Ctrl+] | Menu: Ctrl+T | Help: Ctrl+T followed by Ctrl+H ---
ets Jul 29 2019 12:21:46

rst:0x1 (POWERON_RESET),boot:0x13 (SPI_FAST_FLASH_BOOT)
configsip: 0, SPIWP:0xee
clk_drv:0x00,q_drv:0x00,d_drv:0x00,cs0_drv:0x00,hd_drv:0x00,wp_drv:0x00
mode:DIO, clock div:2
load:0x3fff0030,len:6668
ho 0 tail 12 room 4
load:0x40078000,len:14944
load:0x40080400,len:3816
0x40080400: _init at ??:?

entry 0x40080698
I (29) boot: ESP-IDF v4.4.4-dirty 2nd stage bootloader
I (29) boot: compile time 15:28:37
I (29) boot: chip revision: v3.0
I (33) boot_comm: chip revision: 3, min. bootloader chip revision: 0
I (40) boot.esp32: SPI Speed      : 40MHz
I (44) boot.esp32: SPI Mode       : DIO
I (49) boot.esp32: SPI Flash Size : 2MB
I (53) boot: Enabling RNG early entropy source...
I (59) boot: Partition Table:
I (62) boot: ## Label            Usage          Type ST Offset   Length
I (70) boot:  0 nvs              WiFi data        01 02 00009000 00006000
I (77) boot:  1 phy_init         RF data          01 01 0000f000 00001000
I (85) boot:  2 factory          factory app      00 00 00010000 00100000
I (92) boot: End of partition table
I (96) boot_comm: chip revision: 3, min. application chip revision: 0
I (103) esp_image: segment 0: paddr=00010020 vaddr=3f400020 size=086fch ( 34556) map
I (125) esp_image: segment 1: paddr=00018724 vaddr=3ffb0000 size=02430h (  9264) load
I (128) esp_image: segment 2: paddr=0001ab5c vaddr=40080000 size=054bch ( 21692) load
I (140) esp_image: segment 3: paddr=00020020 vaddr=400d0020 size=15c9ch ( 89244) map
I (173) esp_image: segment 4: paddr=00035cc4 vaddr=400854bc size=063cch ( 25548) load
I (189) boot: Loaded app from partition at offset 0x10000
I (189) boot: Disabling RNG early entropy source...
I (201) cpu_start: Pro cpu up.
I (201) cpu_start: Starting app cpu, entry point is 0x4008102c
0x4008102c: call_start_cpu1 at C:/Espressif/frameworks/esp-idf-v4.4.4/components/esp_system/port/cpu_start.c:148

I (0) cpu_start: App cpu up.
I (215) cpu_start: Pro cpu start user code
I (215) cpu_start: cpu freq: 160000000
I (215) cpu_start: Application information:
I (220) cpu_start: Project name:     app-template
I (225) cpu_start: App version:      1
I (229) cpu_start: Compile time:     Nov  9 2023 15:26:53
I (236) cpu_start: ELF file SHA256:  eb82610d29ee29f4...
I (242) cpu_start: ESP-IDF:          v4.4.4-dirty
I (247) heap_init: Initializing. RAM available for dynamic allocation:
I (254) heap_init: At 3FFAE6E0 len 00001920 (6 KiB): DRAM
I (260) heap_init: At 3FFB2D18 len 0002D2E8 (180 KiB): DRAM
I (266) heap_init: At 3FFE0440 len 00003AE0 (14 KiB): D/IRAM
I (273) heap_init: At 3FFE4350 len 0001BCB0 (111 KiB): D/IRAM
I (279) heap_init: At 4008B888 len 00014778 (81 KiB): IRAM
I (287) spi_flash: detected chip: generic
I (290) spi_flash: flash io: dio
W (294) spi_flash: Detected size(4096k) larger than the size in the binary image header(2048k). Using the size in the binary image header.
I (308) cpu_start: Starting scheduler on PRO CPU.
I (0) cpu_start: Starting scheduler on APP CPU.
I (318) gpio: GPIO[22]| InputEn: 0| OutputEn: 0| OpenDrain: 0| Pullup: 1| Pulldown: 0| Intr:0 
```

#เเสดงได้ ติด/ดับดังภาพ

![image](https://github.com/CHAIYAPRUK/LabSheet-01/assets/115066395/9ae0cc84-bb6a-43a7-b5f6-94929d49e038)

![image](https://github.com/CHAIYAPRUK/LabSheet-01/assets/115066395/7b5850f5-cc0f-44a2-8a86-5b672b19a5ae)


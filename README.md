# esp32-homekit-camera fork
adaptatiom of butiful Maxim Kulkin project for TTGO Camera modul with working OLED display modul, PIR modul.
DHT/BMP sensors soon, as and implementaion of Motion characteristik in to Homekit.


Firmware for esp32-camera module to act as Apple Homekit IP camera.

Based on https://github.com/maximkulkin/esp32-homekit-camera [esp-homekit](https://github.com/maximkulkin/esp-homekit).

For compiling under Windows:
1. Install Espressif-IDF for Windows : https://docs.espressif.com/projects/esp-idf/en/stable/get-started/index.html#get-started-get-esp-idf
2. Add work path as described : https://docs.espressif.com/projects/esp-idf/en/stable/get-started/add-idf_path-to-profile.html#add-idf-path-to-profile-windows
3. Start msys32 and change directory to project's dir cd C:/msys32/home/user-name/esp/esp-idf  (note the slashes)
4. From msys window run "make menuconfig" as below, then "make flash"
 
## Configuration

Before compiling, you need to alter several settings in menuconfig (`make
menuconfig`):
* Partition Table
    * Partition Table = **Custom partition table CSV**
    * Custom partition CSV file = **partitions.csv**
* Component config
    * ESP32-specific
        * Support for external, SPI-connected RAM = **check**
        * SPI RAM config
            * Initialize SPI RAM when booting the ESP32 = **check**
            * SPI RAM access method = **Make RAM allocatable using malloc() as well**
    * Camera configuration
        * OV2640 Support = **check**
* ESP32 HomeKit Camera
    * AP or STA = *your preference*
    * Camera Pins
        * Select Camera Pinout = TTGO_Camera_module_V17

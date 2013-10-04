TARGET_CHIP := NRF51822_QFAA_CA
BOARD := BOARD_PCA10001

C_SOURCE_FILES += main.c
C_SOURCE_FILES += nrf_delay.c

OUTPUT_FILENAME := blinky_gcc
SDK_PATH = ../../nrf51_sdk_v4_4_1_31827/nrf51822/


#Uncomment correct line if you have softdevice programmed on the chip.
DEVICE_VARIANT := xxaa
#DEVICE_VARIANT := xxab

USE_SOFTDEVICE := S110
#USE_SOFTDEVICE := S210

include $(SDK_PATH)Source/templates/gcc/Makefile.common
include Makefile.jlink


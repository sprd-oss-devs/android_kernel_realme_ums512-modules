# mali_gondul.o

#need to be defined in device dir
$(warning BSP_BOARD_NAME: $(BSP_BOARD_NAME))
TARGET_BOARD := $(BSP_BOARD_NAME)

BSP_KERNEL_PATH := $(KERNEL_SRC)
CURDIR := $(KERNEL_SRC)/$(M)
KO_MODULE_NAME := mali_gondul
KO_MODULE_OUT := $(M)

all: modules

modules:
	$(MAKE) -C $(CURDIR)/mali CONFIG_MALI_PLATFORM_NAME=$(MALI_PLATFORM_NAME) CONFIG_MALI_BOARD_PLATFORM=$(TARGET_BOARD_PLATFORM) CONFIG_TARGET_BOARD=$(TARGET_BOARD) CONFIG_MALI_VOLTAGE_LEVEL=$(VOLTAGE_CONTROLLER_LEVEL) KDIR=$(BSP_KERNEL_PATH) M=$(KO_MODULE_OUT) src=$(CURDIR)/mali modules

modules_install:
	$(MAKE) -C $(BSP_KERNEL_PATH) M=$(KO_MODULE_OUT) modules_install

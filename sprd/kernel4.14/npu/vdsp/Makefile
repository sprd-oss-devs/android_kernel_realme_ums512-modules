#
# sprd_vdsp.ko
#
# Makefile: for external make invocation
#
# Note:
# - Please refer to modules/sample/Makefile to find out what should be
#   done in this Makefile
#

BSP_KERNEL_PATH := $(KERNEL_SRC)
CURDIR := $(KERNEL_SRC)/$(M)
KO_MODULE_NAME := sprd_vdsp
KO_MODULE_OUT := $(M)

all: modules

ifneq ($(BSP_BOARD_CAMERA_MODULE_VDSP_DEVICE),Cadence)
modules modules_install clean:
	@echo "Skipped, Kbuild only for Cadence vdsp!"
else
modules:
	$(MAKE) -C $(BSP_KERNEL_PATH) M=$(KO_MODULE_OUT) src=$(CURDIR) modules

modules_install:
	$(MAKE) -C $(BSP_KERNEL_PATH) M=$(KO_MODULE_OUT) modules_install

clean:
	$(MAKE) -C $(BSP_KERNEL_PATH) M=$(KO_MODULE_OUT) src=$(CURDIR) clean
endif

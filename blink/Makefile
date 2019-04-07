PROJECT = blink
BUILD_DIR = bin

#SHARED_DIR = ../my-common-code
CFILES = miniblink.c
CFILES += 
AFILES += 

# TODO - you will need to edit these two lines!
DEVICE=stm32f407vet6
#OOCD_FILE = board/stm32f4discovery.cfg

# You shouldn't have to edit anything below here.
VPATH += $(SHARED_DIR)
INCLUDES += $(patsubst %,-I%, . $(SHARED_DIR))
OPENCM3_DIR=../libopencm3

include $(OPENCM3_DIR)/mk/genlink-config.mk
include ../rules.mk
include $(OPENCM3_DIR)/mk/genlink-rules.mk

bin:
	arm-none-eabi-objcopy -O binary $(notdir $(CURDIR)).elf $(notdir $(CURDIR)).bin

#for use with dfu-util (usb programming, boot jumpers must be set BOOT0=1, BOOT1=0)
dfu: $(ELF)	
	sudo dfu-util -d 0483:df11 -a 0 -s 0x08000000 -D $(notdir $(CURDIR)).bin

#for use with st-flash (programming using the stlink)
burn: $(ELF)
	st-flash write $(notdir $(PROJECT)).bin 0x8000000
	

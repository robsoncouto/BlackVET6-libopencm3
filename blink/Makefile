PROJECT = blink
BUILD_DIR = bin

#SHARED_DIR = ../my-common-code
CFILES = miniblink.c
CFILES += 
AFILES += 

# TODO - you will need to edit these two lines!
DEVICE=stm32f030f4p6
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

burn: $(ELF)	
	st-flash write $(notdir $(PROJECT)).bin 0x8000000

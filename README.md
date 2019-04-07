blink template for the STM32F4 using libopencm3.
Template forked from the [libopencm3 one](https://github.com/libopencm3/libopencm3-template).

# Instructions
 1. git clone https://github.com/libopencm3/libopencm3-template.git your-project
 2. cd blink
 3. git submodule update --init # (Only needed once)
 4. make -C libopencm3 # (Only needed once)
 5. make -C blink

# Directories
* `blink`: contains the application, can be renamed (but don't forget to update the makefile)

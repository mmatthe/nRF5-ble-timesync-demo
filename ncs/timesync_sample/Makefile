##
# Project Title
#
# @file
# @version 0.1

build52:
	nrfutil toolchain-manager launch -- west build --build-dir build52 --board nrf52840dongle .

flash52:
	nrfutil nrf5sdk-tools pkg generate --hw-version 52 --sd-req=0x00 --application build52/timesync_sample/zephyr/zephyr.hex --application-version 1 build52/app.zip && \
	pkill -9 minicom;  \
	nrfutil dfu usb-serial -pkg build52/app.zip -p /dev/ttyACM0 ;  \
	nrfutil dfu usb-serial -pkg build52/app.zip -p /dev/ttyACM1 ;  \

build53:
	nrfutil toolchain-manager launch -- west build --build-dir build53 . --board nrf5340dk/nrf5340/cpuapp

flash53:
	nrfutil toolchain-manager launch west flash --build-dir build53; \

.PHONY: flash52 build52 serial help clean pristine

# end

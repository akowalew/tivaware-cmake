cmake_minimum_required(VERSION 3.10.2 FATAL_ERROR)

project(tivaware-cmake VERSION 0.1.0 LANGUAGES C)

add_library(tivaware_driverlib
	src/driverlib/adc.c
	src/driverlib/aes.c
	src/driverlib/can.c
	src/driverlib/comp.c
	src/driverlib/cpu.c
	src/driverlib/crc.c
	src/driverlib/des.c
	src/driverlib/eeprom.c
	src/driverlib/emac.c
	src/driverlib/epi.c
	src/driverlib/flash.c
	src/driverlib/fpu.c
	src/driverlib/gpio.c
	src/driverlib/hibernate.c
	src/driverlib/i2c.c
	src/driverlib/interrupt.c
	src/driverlib/lcd.c
	src/driverlib/mpu.c
	src/driverlib/onewire.c
	src/driverlib/pwm.c
	src/driverlib/qei.c
	src/driverlib/shamd5.c
	src/driverlib/ssi.c
	src/driverlib/sw_crc.c
	src/driverlib/sysctl.c
	src/driverlib/sysexc.c
	src/driverlib/systick.c
	src/driverlib/timer.c
	src/driverlib/uart.c
	src/driverlib/udma.c
	src/driverlib/usb.c
	src/driverlib/watchdog.c
)

add_library(TivaWare::driverlib ALIAS tivaware_driverlib)

target_include_directories(tivaware_driverlib
	PUBLIC
		$<INSTALL_INTERFACE:include>
		$<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
	PRIVATE
		${CMAKE_CURRENT_SOURCE_DIR}/src
		${CMAKE_CURRENT_SOURCE_DIR}/include/tivaware
)

target_compile_definitions(tivaware_driverlib
	PUBLIC
		-Dgcc
)

target_compile_options(tivaware_driverlib
	PRIVATE
		-Wall
		-Werror
		-ffunction-sections
		-fdata-sections
		-fno-exceptions
		-fno-unwind-tables
		-fno-asynchronous-unwind-tables
		--specs=nano.specs
		-std=c11
)

export(PACKAGE TivaWare)

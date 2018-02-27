add_library(tivaware_utils
	uartstdio.c
	ustdlib.c
)

target_link_libraries(tivaware_utils
	tivaware_driverlib
)

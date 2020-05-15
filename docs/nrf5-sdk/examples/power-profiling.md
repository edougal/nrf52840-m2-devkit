# Power Profiling Example

## Description

The Power Profiling Example demonstrates how to place the board into a minimum power consumption state and perform the real-time current profiling.

This example application starts up, sends the Deep Power-down (DP) instruction to the QSPI flash memory and puts the TFT LCD into sleep mode. When the USER button is pressed, the board enters the System OFF mode. The current can be measured by the advanced power profiling module on M.2 Dock.

!!! Tip
	Before you start building, remember to set up the nRF5 SDK development environment first. See [Setup the nRF5 SDK](../setup.md) for details.


## Building the example

You can find the source code and the project file of the example in the following folder: [examples/nrf5-sdk/pwr_mgmt](https://github.com/makerdiary/nrf52840-m2-devkit/tree/master/examples/nrf5-sdk/pwr_mgmt).

Open terminal and navigate to the directory with the example Makefile:

``` sh
cd ./examples/nrf5-sdk/pwr_mgmt/armgcc
```

Run `make` to build the example:

``` sh
make
```

## Programming the firmware

If compiled successfully, the firmware is located in `pwr_mgmt/armgcc/_build` with the name `nrf52840_xxaa.hex`.

Connect the debugger USB port to your PC using the provided USB-C Cable. A disk drive called **M2-DOCK** will be automatically detected by the computer.

![](../assets/images/programming-firmware.png)

Drag and drop the firmware `nrf52840_xxaa.hex` onto the **M2-DOCK** drive, or run the following command in `pwr_mgmt/armgcc` to program the board:

``` sh
make flash
```

!!! Tip
	See **[Programming](../../programming.md)** section for details about how to program the nRF52840 M.2 Module.

## Testing

Measure the appplication current by performing the following steps:

1. Connect the debugger USB port to your PC

2. When the **M2-DOCK** drive appears, navigate to the `tools` directory and run:

	``` sh
	python3 power-profiler.py
	```

3. Zoom in the current axis to the best view and observe the current curve

4. Press the USER button and observe the curve is sloping down.

!!! Tip
	See **[Power Profiling](../../power-profiling.md)** section for details about how to perform the real-time current profiling.

## Create an Issue

Interested in contributing to this project? Want to report a bug? Feel free to click here:

<a href="https://github.com/makerdiary/nrf52840-m2-devkit/issues/new?title=nRF5%20SDK-Power%20Profiling:%20%3Ctitle%3E"><button data-md-color-primary="red-bud"><i class="fa fa-github"></i> Create an Issue</button></a>
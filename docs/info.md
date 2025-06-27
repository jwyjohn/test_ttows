<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

The circuit processes 8-bit input data through a series of NOT gates and routes the results to both internal processing and external display. Here's the signal flow:

**Input Processing:**

- 8-bit DIP switch (sw1) provides parallel input data
- Each switch connects to external inputs (EXTIN0-EXTIN7) on the TinyTapeout input block
- Switches are pulled high when closed, creating active-high logic

**Logic Processing:**

- Four NOT gates (not1-not4) invert the first four input bits
- Inverted signals connect to outputs OUT0-OUT3
- Remaining inputs (IN4-IN7) pass directly through to outputs OUT4-OUT7

**Clock and Control:**

- Clock generator (10kHz) provides system timing
- Slide switch (sw2) enables/disables clock signal
- Step button (btn1) allows manual clock stepping for debugging
- Reset button (btn2) with pull-up resistor provides system reset

**Output Display:**

- 7-segment display shows processed data
- External outputs EXTOUT0-EXTOUT6 drive segments A-G
- EXTOUT7 drives decimal point
- Common cathode configuration with ground connection

## How to test

**Basic Functionality Test:**

1. Set all DIP switches to OFF position initially
2. Power on the circuit - 7-segment display should show "0"
3. Toggle individual DIP switches and observe display changes
4. Verify that the first 4 bits are inverted in the output

**Clock Control Test:**

1. Set slide switch (sw2) to enable clock mode
2. Observe automatic updates on the 7-segment display
3. Switch to manual mode and use step button for single-step operation
4. Verify timing with 10kHz clock frequency

**Reset Test:**

1. Configure switches to create a known pattern
2. Press reset button (btn2)
3. Verify system returns to initial state
4. Test reset functionality in both clock modes

**Input/Output Verification:**

- Test each DIP switch individually
- Verify NOT gate operation on bits 0-3
- Confirm direct pass-through on bits 4-7
- Check 7-segment display correspondence

## External hardware

**Required Components:**

- **8-position DIP switch**: Provides 8-bit parallel input data
- **7-segment display (common cathode)**: Shows processed output data
- **Clock generator**: 10kHz frequency source for automatic operation
- **Slide switch**: Clock mode selection (auto/manual)
- **Push buttons (2x)**: Step control and system reset
- **Pull-up resistor**: 1kΩ for reset button
- **Power supplies**: VCC and GND connections

**Pin Connections:**

- **External Inputs (EXTIN0-7)**: Connect to DIP switch outputs
- **External Clock (EXTCLK)**: Connect to clock control circuit
- **External Reset (EXTRST_N)**: Connect to reset button with pull-up
- **External Outputs (EXTOUT0-7)**: Connect to 7-segment display

**Interface Specifications:**

- **Logic levels**: Standard TTL/CMOS (0V/3.3V or 0V/5V)
- **Current requirements**: Standard digital logic levels
- **Clock frequency**: Up to 10kHz (configurable)
- **Reset**: Active-low with pull-up resistor

**Physical Setup:**

1. Mount DIP switch for easy access to all 8 positions
2. Position 7-segment display for clear visibility
3. Place control buttons (step/reset) in accessible locations
4. Ensure proper power distribution to all components
5. Verify ground connections for 7-segment display common cathode

**Testing Equipment:**

- Logic analyzer or oscilloscope for signal verification
- Multimeter for power supply and continuity checks
- Function generator (optional) for alternative clock sources

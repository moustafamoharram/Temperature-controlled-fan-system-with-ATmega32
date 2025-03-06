# Temperature-controlled-fan-system-with-ATmega32
Project Overview

This project designs a temperature-controlled fan system using the ATmega32 microcontroller. The fan speed adjusts automatically based on temperature readings from an LM35 sensor, with real-time data displayed on an LCD. The fan’s speed is controlled through PWM signals generated by Timer0.

Features
	•	Automatic Fan Control: The fan turns on or off based on temperature thresholds.
	•	Dynamic Speed Adjustment:
	•	< 30°C → Fan OFF
	•	≥ 30°C → 25% speed
	•	≥ 60°C → 50% speed
	•	≥ 90°C → 75% speed
	•	≥ 120°C → 100% speed
	•	Real-Time LCD Display: Temperature value and fan state are continuously shown.
	•	PWM Control: Fan speed controlled via Timer0-generated PWM signals.

Hardware Components
	•	ATmega32 Microcontroller (1 MHz clock)
	•	LM35 Temperature Sensor
	•	DC Motor (as a fan)
	•	LCD Display (8-bit mode)
	•	Transistors, resistors, and wiring

Pin Configuration
	•	LM35 Sensor: Connected to ADC channel 2
	•	LCD Pins:
	•	RS → PD0
	•	RW → GND
	•	E → PD2
	•	Data Bus → PORTC

System Architecture

The project follows a layered architecture:
	•	ADC Driver: Converts analog temperature data to digital values (polling-based).
	•	GPIO Driver: Handles pin configurations for LCD and DC motor.
	•	LCD Driver: Displays temperature and fan state.
	•	DC Motor Driver: Controls motor speed and direction.
	•	PWM Driver: Generates PWM signals (500Hz) with Timer0 for speed control.

How It Works
	1.	The LM35 sensor continuously measures temperature.
	2.	ADC converts the sensor’s analog signal to a digital value.
	3.	The microcontroller calculates the temperature and updates the LCD.
	4.	Based on the temperature, the PWM duty cycle adjusts the fan speed.

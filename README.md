# Automotive Performance Package Simulation

This repository contains a Simulink model that simulates the logic for an automotive performance package. The system adjusts the car's behavior in response to sensor data, specifically speed and lateral acceleration, to decide between "High Performance" and "Economy" modes.

## Overview

Modern vehicles utilize numerous computers to process data from hundreds of sensors. In this simplified system, we focus on two key parameters:

- **Speed**
- **Lateral Acceleration**

The model uses these inputs to switch between performance modes based on specific conditions.

## Logic Description

The Simulink model includes the following logic:

1. **Sensor Data Input:**
   - The **Signal Editor** block simulates speed and lateral acceleration data.

2. **Conditions for High Performance Mode:**
   - Speed >= 100 km/h
   - OR (Speed >= 35 km/h AND |Lateral Acceleration| >= 3 m/s²)

3. **Mode Selection:**
   - If any of the above conditions are true, the vehicle switches to **High Performance Mode** (Output = 2).
   - Otherwise, it remains in **Economy Mode** (Output = 1).

4. **Signal Assessment:**
   - The final output is evaluated using the **Signal Assessment** block.

## How to Run

1. Open the model in Simulink.
2. Run the simulation.
3. Use a **Scope** block to visualize the sensor data and mode selection output.

## Prerequisites

- MATLAB with Simulink
- Basic understanding of Simulink blocks (AND, OR, Relational Operator, Signal Editor, etc.)

## Model Components

- **Signal Editor:** Generates simulated sensor data.
- **Relational Operators:** Compare speed and lateral acceleration with threshold values.
- **Logical Operators:** Combine conditions for mode selection.
- **Switch Block:** Determines the output mode.
- **Signal Assessment:** Validates the output.

## Training Context

This project was created as part of the **Simulink Onramp** training provided by MathWorks.

## License

This project is licensed under the MIT License.


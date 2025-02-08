# Simulink Projects Repository

This repository contains multiple Simulink models showcasing different control and simulation systems. These projects were created as part of the **Simulink Onramp** training provided by **MathWorks**.

## Projects Overview

### 1. Automotive Performance Package Simulation

This project simulates the logic for an automotive performance package. The system adjusts the car's behavior in response to sensor data, specifically speed and lateral acceleration, to decide between "High Performance" and "Economy" modes.

#### Logic Description

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

#### How to Run

1. Open the model in Simulink.
2. Run the simulation.
3. Use a **Scope** block to visualize the sensor data and mode selection output.

#### Model Components

- **Signal Editor:** Generates simulated sensor data.
- **Relational Operators:** Compare speed and lateral acceleration with threshold values.
- **Logical Operators:** Combine conditions for mode selection.
- **Switch Block:** Determines the output mode.
- **Signal Assessment:** Validates the output.

### 2. Thermostat Model

In this project, we model the discrete equations representing a PI (Proportional-Integral) controller. The model simulates the temperature dynamics of a house, aiming to maintain a comfortable environment by adjusting control efforts based on current and desired temperatures.

#### Control System Description

- **First-Order Cooling Equation:** Represents the temperature dynamics of the house.
- **PI Controller:** Integrates the error and increases control effort as the accumulated error grows.
- **Set Temperature:** A constant representing the desired room temperature.
- **House Block:** Models the house’s thermal behavior based on external conditions and control inputs.

#### How to Run

1. Open the model in Simulink.
2. Set the desired temperature.
3. Run the simulation to observe how the PI controller maintains the target temperature.

#### Model Components

- **Error Calculation:** Difference between desired and actual temperature.
- **Proportional Control:** Immediate response based on current error.
- **Integral Control:** Response based on accumulated past errors.
- **House Dynamics:** Models how temperature changes over time.

### 3. Peregrine Falcon Dive Dynamics Model

When diving for prey, the Peregrine falcon can reach speeds of up to 350 km/h. As the falcon dives, the two forces acting on it are gravity and air drag. The equation of motion for this is:

**m * v̇ = (1/2) * ρ * Cd * A * v² - mg**

As it approaches the ground, the falcon changes the angle of its wings, increasing drag and rapidly decelerating to a safe landing speed. This behavior is modeled by adjusting the drag coefficient (**Cd**) and area (**A**).

#### Model Description

1. **Equation of Motion:** Models the dynamics of the falcon during its dive.
2. **Drag Adjustment:** Simulates the change in drag as the wings open when the speed exceeds 15 m/s.
3. **Forces Acting:** Considers gravitational force and air drag.

#### How to Run

1. Open the model in Simulink.
2. Run the simulation.
3. Use the **Scope** block to observe velocity and height changes during the dive and deceleration phases.

#### Model Components

- **Gravitational Force (m * g):** Acts downward throughout the dive.
- **Air Drag:** Varies with speed and wing configuration (Low Drag and High Drag conditions).
- **Switch Block:** Changes drag parameters based on speed threshold.
- **Integrators:** Calculate velocity and height over time.
- **Model Assessment:** Validates the simulation output.

## Prerequisites

- MATLAB with Simulink
- Basic understanding of Simulink blocks (AND, OR, Relational Operator, Signal Editor, PI Controller, etc.)

## Contributing

Contributions are welcome. Please fork the repository, make your changes, and submit a pull request.

## License

This project is licensed under the MIT License.

---

**Note:** All projects in this repository were created as part of the **Simulink Onramp** training on **MathWorks**.


# Quadcopter Flight Stabilization Simulation

This project is a Python-based numerical simulation of a simplified quadcopter stabilization system. The simulation focuses on single-axis roll stabilization using a proportional-derivative (PD) controller, discrete-time numerical integration, and an IMU-style sensor model.

The goal of the project is to model how a quadcopter can correct its roll angle after an initial tilt or disturbance and return to a stable equilibrium position.

## Project Description

The simulation models the roll angle of a quadcopter using two main state variables:

- `theta`: roll angle in radians
- `omega`: angular velocity in radians per second

The system uses a PD controller to compute a corrective control input. The controller attempts to drive the roll angle back to zero while damping angular velocity to avoid unstable oscillations.

A disturbance is applied at `t = 1.0 s` to test whether the system can reject a sudden change in orientation and return to equilibrium.

## Numerical Methods Used

This project uses discrete-time numerical integration to update the system state over time. The simulation runs at:

```python
dt = 1 / 250
# README for Mosquito Population Dynamics Model 3

## Overview
This repository contains the implementation of Model 3 for mosquito population dynamics. This model incorporates various factors including delays in developmental stages, environmental carrying capacity, and control measures such as insecticides or biological control. The primary goal of the model is to simulate and understand the effects of these factors on adult mosquito populations over time.

## Model Description
The model is a differential equation that predicts the number of adult mosquitoes (`N(t)`) at any given time `t`, considering:

- **Daily Egg Laying Rate (r)**: Number of eggs laid per adult mosquito per day.
- **Environmental Carrying Capacity (K)**: The maximum population that the environment can sustain.
- **Natural Mortality Rate (μ)**: The natural rate at which adult mosquitoes die.
- **Control Measure Mortality Rate (μ_c)**: Additional mortality rate due to applied control measures.
- **Developmental Delay (τ)**: Time delay from egg to adult mosquito in days.
- **Mosquito Population at Time t (N(t))**: Number of adult mosquitoes at time t.
- **New Adult Mosquitoes at Time t (N(t - τ))**: Number of new adult mosquitoes generated at time (t - τ) that become adults at time t.

The differential equation used to model the dynamics is structured to consider both the carrying capacity limit (`K`) and the total mortality rate (considering both natural and control-induced deaths).

## Algorithm Design
1. **Initialization**:
   - Set the time step `Δt` (e.g., 1 day).
   - Set total simulation time `T` (e.g., 100 days).
   - Initialize adult mosquito population `N(0)`.

2. **Time Discretization**:
   - Time is discretized into steps from `t=0` to `t=T` with steps of `Δt`.

3. **Numerical Solution**:
   - Use Euler's method to update `N(t)` for each time point `t`.
   - Consider developmental delay `τ` to calculate `N(t-τ)` which might require initialization of `N` values prior to simulation start.

4. **Repetition and Updating**:
   - Repeat the calculation until the end of the simulation time `T`.

5. **Output**:
   - Store or output `N(t)` for further analysis or visualization.

## Usage Instructions
### Prerequisites
Ensure you have Python installed along with the following packages:
- `numpy`
- `matplotlib`

### Running the Model
1. Clone this repository to your local machine.
2. Navigate to the directory containing the script.
3. Run the script using Python:
   ```
   python mosquito_population_model.py
   ```

### Output
The output will be a plot showing the dynamics of the mosquito population over time, considering the given parameters. The plot visually represents how the population grows or declines based on the specified initial conditions and parameters.

## Additional Considerations
- **Survival Rate from Egg to Adult**: This could be added to refine the model.
- **Variable Parameters**: Factors like `r`, `K`, `μ`, and `τ` could be made variable over time or conditions.
- **Disease Impact**: The impact of diseases on mosquito populations can also be incorporated for a more comprehensive model.

By utilizing this model, researchers and public health officials can better understand and predict mosquito population dynamics, aiding in the effective planning and implementation of control strategies.

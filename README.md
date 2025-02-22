# Router Optimization using Firefly Algorithm

This repository contains Python code that implements the **Firefly Algorithm** for optimizing router placement in wireless networks. The algorithm aims to maximize both **coverage** and **connectivity** by iteratively adjusting the positions of routers.

## Key Concepts

### Coverage
The coverage of a router configuration is determined by the number of clients within the router's coverage radius.

### Connectivity
Connectivity is defined as the number of clients that are connected to the network through the routers' coverage.

### Fitness
The fitness function combines coverage and connectivity to evaluate the quality of a router configuration.

## Variables

- `num_clients`: Number of clients in the network.
- `num_routers`: Number of routers to be placed.
- `coverage_radius`: Radius of router coverage in network units.
- `area_size`: Width and height of the area in network units.
- `max_iter`: Maximum number of iterations for the optimization process.
- `num_fireflies`: Number of fireflies (population size).
- `alpha`: Randomness strength parameter.
- `beta_0`: Attraction coefficient base.
- `gamma`: Absorption coefficient, affecting the balance between coverage and connectivity.

## Firefly Algorithm Overview

The firefly algorithm optimizes router placement through the following steps:

1. **Initialization**: Randomly place fireflies (routers) in the area.
2. **Coverage & Connectivity Calculation**: Calculate the coverage and connectivity for each firefly.
3. **Fitness Evaluation**: Evaluate each firefly's fitness using the coverage, connectivity, and user-defined parameters.
4. **Movement**: Fireflies move toward brighter (better) fireflies based on their fitness.
5. **Iteration**: Repeat the process for multiple generations, adjusting parameters like `alpha` and `beta_0`.
6. **Termination**: The algorithm stops once the maximum number of iterations is reached or a convergence criterion is met.

## Euclidean Distance Formula

The Euclidean distance formula is used to measure the distance between two router configurations (fireflies). The formula is:

\[
d(P, Q) = \sqrt{(x_1 - x_2)^2 + (y_1 - y_2)^2}
\]

Where:
- \(P\) and \(Q\) are two router configurations (fireflies).
- \((x_1, y_1)\) and \((x_2, y_2)\) are the positions of the routers.

This distance is used to guide the movement of fireflies toward better solutions during optimization.

## Plotting Coverage

The algorithm visualizes the optimized router placements using **Matplotlib**. The plot displays:

- **Client Positions**: Blue dots indicating the locations of clients.
- **Router Positions**: Red stars indicating the optimized positions of the routers.
- **Coverage Radius**: Green circles representing the coverage area of each router.

### Example Output

After running the algorithm, the plot will display:

- **Blue dots**: Client positions in the network area.
- **Red stars**: Final optimized router positions.
- **Green circles**: Coverage radius for each router, illustrating the area covered by each router.

This helps to visualize the success of the algorithm in maximizing coverage and connectivity.

## Requirements

- Python 3.x
- Libraries:
  - `numpy`
  - `matplotlib`

You can install the required libraries using `pip`:

```bash
pip install numpy matplotlib

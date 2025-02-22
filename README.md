# Router Optimization using Firefly Algorithm

This repository implements a firefly algorithm to optimize router placement in wireless networks. The algorithm maximizes coverage and connectivity by iteratively adjusting router positions based on a bio-inspired optimization approach.

## Core Components

### Optimization Parameters
- Number of clients
- Number of routers
- Coverage radius
- Area dimensions
- Maximum iterations
- Population size (number of fireflies)
- Algorithm coefficients (α, β₀, γ)

### Key Metrics
- **Coverage**: Percentage of clients within router range
- **Connectivity**: Number of clients connected to the network
- **Fitness**: Combined metric of coverage and connectivity quality

## Algorithm Overview

1. **Initialization**: Random placement of router positions
2. **Evaluation**: Calculate coverage and connectivity metrics
3. **Optimization**: Iterative improvement through firefly movement
4. **Movement**: Routers (fireflies) move toward better configurations
5. **Convergence**: Process continues until reaching stop criteria

## Distance Calculation

The algorithm uses Euclidean distance to measure configuration similarity:

```python
distance = sqrt((x₂ - x₁)² + (y₂ - y₁)²)
```

Where:
- (x₁, y₁): Position of first router
- (x₂, y₂): Position of second router

## Visualization

The output plot shows:
- Client locations (blue dots)
- Optimal router positions (red stars)
- Coverage areas (green circles)

## Usage

```python
# Initialize optimizer
optimizer = RouterOptimizer(
    num_clients=50,
    num_routers=15,
    coverage_radius=200,
    area_size=2000
)

# Run optimization
best_positions = optimizer.optimize()

# Visualize results
optimizer.plot_results()
```

## Implementation Details

The optimization process uses the following key methods:

1. **Firefly Movement**:
   - Brighter fireflies attract others
   - Movement influenced by distance and attractiveness

2. **Fitness Calculation**:
   - Combines coverage and connectivity scores
   - Weighted by user-defined parameters

3. **Coverage Assessment**:
   - Checks client coverage within radius
   - Evaluates network connectivity

![Sample Output](Router.png)
*Figure: Visualization of optimized router placement showing clients (blue dots), routers (red stars), and coverage areas (green circles)*
The visualization module uses Matplotlib to create clear, informative plots of the network configuration.

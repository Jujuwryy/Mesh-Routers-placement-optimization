Router Optimization using Firefly Algorithm

This repository contains Python code that implements a firefly algorithm for optimizing router placement in wireless networks. The algorithm aims to maximize both coverage and connectivity by iteratively adjusting router positions.

## Formulas and Variables

### Formulas

- **Coverage**: The coverage of a router configuration is calculated based on the number of clients covered by the routers within the coverage radius.
- **Connectivity**: The connectivity is determined by the number of clients that are connected to the network through the routers' coverage.
- **Fitness**: The fitness function combines coverage and connectivity to evaluate the quality of a router configuration.

### Variables

- `num_clients`: Number of clients in the network.
- `num_routers`: Number of routers to be placed.
- `coverage_radius`: Radius of router coverage in network units.
- `area_size`: Width and Height of the area in network units.
- `max_iter`: Maximum number of iterations for the optimization process.
- `num_fireflies`: Number of fireflies (population size).
- `alpha`: Randomness strength parameter.
- `beta_0`: Attraction coefficient base.
- `gamma`: Absorption coefficient (affects the balance between coverage and connectivity).

## Algorithm

The firefly algorithm optimizes router placement through the following steps:

1. Initialize fireflies (router positions) randomly.
2. Calculate coverage and connectivity for each firefly.
3. Evaluate fitness for each firefly using the coverage, connectivity, and user-defined parameters.
4. Move fireflies towards brighter (i.e., better) fireflies based on their fitness.
5. Iterate through multiple generations, adjusting parameters like alpha and beta_0.
6. Terminate when the maximum number of iterations is reached or a convergence criterion is met.

## Euclidean Distance Formula

The Euclidean distance formula is a fundamental concept in mathematics, used to measure the distance between two points in a two-dimensional space. In the context of this router optimization problem and the firefly algorithm, the Euclidean distance formula is utilized to calculate the distance between two router configurations (fireflies).

The Euclidean distance between two points \( P(x_1, y_1) \) and \( Q(x_2, y_2) \) in a two-dimensional Cartesian coordinate system is given by:

\[ d(P, Q) = \sqrt{(x_2 - x_1)^2 + (y_2 - y_1)^2} \]

In the context of the firefly algorithm for router optimization:

- \( P \) and \( Q \) represent two router configurations (fireflies).
- \( (x_1, y_1) \) and \( (x_2, y_2) \) are the positions of the routers in the configurations.

By calculating the Euclidean distance between two router configurations, the algorithm can determine how "close" or "far" they are from each other in the solution space. This information is then used to guide the movement of fireflies towards more favorable configurations during the optimization process.

In the code, the Euclidean distance formula is applied to calculate the distance between the centroids of two fireflies using their router positions. This distance is crucial for determining the attraction between fireflies, influencing their movement towards better configurations.


## Plot Graph with Coverage

The code visualizes the optimal router positions with coverage radius using Matplotlib. The plot displays the client positions (blue dots), optimal router positions (red stars), and coverage radius of each router (green circles).


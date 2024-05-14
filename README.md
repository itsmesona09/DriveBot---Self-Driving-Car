# DriveBot Self-Driving Cars

- DriveBot is a project aimed at implementing a self-driving car using a neural network built from scratch in JavaScript, without relying on any external libraries.
- The focus of this implementation is to demonstrate the core concepts and algorithms behind self-driving technology.

## car.js
- The Car class simulates a car object in a driving environment, supporting both AI and manual controls.
- It includes properties for position, size, speed, and control type, and initializes sensors and a neural network for AI-driven cars.
- The update method handles movement, collision detection, and AI decision-making based on sensor readings.
- The car's movement is managed by the #move method, which applies acceleration, friction, and updates the car's position and angle.
- The class also includes methods for creating a collision-detection polygon and assessing damage. Additionally, it provides a draw method for rendering the car and its sensors on a canvas.

## controls.js
- The Controls class manages user input for controlling a car in a driving simulation.
- It initializes control states (forward, left, right, reverse) and sets them based on the specified control type.
- For keyboard control, it sets up event listeners to update the control states based on arrow key presses. For dummy control, it defaults to moving forward.
- This class allows for flexible control schemes, enabling both manual and automated car operation in the simulation.

## main.js
- The Car class represents individual cars, which can be controlled either manually or by an AI.
- The Road and Controls classes define the driving environment and user controls, respectively.
- A Sensor class is used for collision detection and environment sensing.
- The NeuralNetwork class processes inputs from the sensors to guide AI-driven cars.
- The Visualizer class draws the neural network's structure. The simulation creates a road with multiple lanes and a traffic array of dummy cars.
- It generates AI cars, allows saving and discarding the best-performing car's brain, and updates the simulation frame by frame using the animate function, continuously drawing the cars and visualizing the neural network.

## network.js
- The NeuralNetwork class implements a simple feedforward neural network with multiple levels, each represented by the Level class.
- Each level has a number of inputs, outputs, biases, and weights, which are initialized to random values.
- The feedForward method allows inputs to be processed through the network, producing outputs.
- The mutate method randomly alters the network's biases and weights to simulate genetic evolution.
- The Level class handles the internal mechanics of individual layers, including random initialization and processing inputs to produce outputs based on the current weights and biases.
- This setup is used to control the behavior of AI-driven cars in a self-driving car simulation.

## road.js
- The Road class simulates a road for a self-driving car simulation.
- It defines the road's position, width, and lane count, and calculates the boundaries and lane centers.
- The draw method renders the road on a canvas, showing lane dividers and borders, providing a visual representation for the simulation environment.

## sensor.js
- The Sensor class equips a self-driving car with a sensory system using rays to detect obstacles.
- It casts rays from the car, checks for intersections with road borders and traffic, and records the closest points.
- The update method processes these detections, #castRays calculates ray positions, and #getReading finds intersections.
- The draw method visualizes the rays on a canvas, helping the car navigate by sensing its environment.

## visulaizer.js
- The Visualizer class provides methods to visualize neural network architectures on a canvas.
- The drawNetwork method renders the entire network, organizing its levels vertically with appropriate spacing.
- Each level is represented by nodes and connections, with input nodes positioned at the bottom and output nodes at the top.
- The drawLevel method draws the nodes and connections for a specific level, including input and output labels if provided.
- Additionally, it defines the visual representation of nodes, connections, and biases.

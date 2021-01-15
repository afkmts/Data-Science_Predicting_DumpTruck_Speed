# Feedforward ANN for predicting linearly dependent data
# Problem Statement
As part of this practical work, the problem of predicting the speed of a dump truck when performing transport and technological processes in a quarry using a neural network of direct propagation will be investigated. The result of the work implies obtaining the most accurate forecast value of the dump truck speed in response to a vector of known or interesting parameters (coordinates, direction of movement, weight of the load), which, as we think, have a linear relationship. Obviously, for a better understanding of the problem, we will give a brief description of the process:
A quarry is a complex and dangerous production system, where a number of activities are carried out to extract and move rock with minerals. Transportation of rock from mining sites (excavator sites) to warehouses is carried out using heavy-duty dump trucks (such as Caterpillar, BelAZ, etc.) on an extensive network of roads. The speed at which dump trucks move depends on the direct amount of rock transported - the subsequent profit of the enterprise. At the same time, the speed of dump trucks is limited by safety rules (no more than 40 km / h) and varies depending on the direction of movement (when descending for loading - higher, when climbing for unloading - lower). To control the speed and other parameters of operation, each dump truck is equipped with a complex of on-board telemetry-sensors, computing devices and data transmission devices. Data is transmitted to the server and provided to the dispatcher system, which coordinates and optimizes the operation of all equipment in the quarry.
# Datasets, Features and Target value
The file truck.xlsx  is a real download of data from the on-board systems of heavy-duty dump trucks of one of the mining enterprises for some time. Every four seconds, the following information was read from all active agents (dump trucks). We have a dataset of dump trucks. This dataset contains 22 parameters:
1. Time - system date and time;
2. control id - system ID of the agent;
3. Vehicle_type - agent type (dump truck or excavator);
4. vehicle_id - ID of the physical agent (tail number of the dump truck);
5. lat - GPS latitude value at a time;
6. lon - GPS longitude value at a time;
7. height - GPS altitude value at a time;
8. Course - the value of direction (azimuth) from GPS;
9. speed - speed of movement;
10. X - latitude value in an unknown coordinate grid;
11. Y - longitude value in an unknown coordinate grid;
12. distance - distance covered by the dump truck since the previous time;
13. fuel - amount of fuel in the tank;
14. weight  - weight of cargo in the body at a time;
15. num_satellite - number of visible satellites at a time;
16. gps_quality - quality (accuracy) of GPS coordinate values;
17. sender - unknown value;
18. link_quality - quality (accuracy?) communication;
19. mes_number - empty unknown value;
20. type - unknown value;
21. received - unknown value;
22. fix_status - number of status changes.

# Steps

Building the Regression Model using Python(Keras) and MATLAB
1. Download the file truck.xlsx 
2. Open the file and filter the data by the Vehicle_type attribute, selecting the value truck.
3. Copy the resulting array and save it to a separate file.
4. Carefully perform data exploration in accordance with the guidelines. Don't forget to remove explicit outliers while maintaining the integrity of the table structure. For example, note that the weight attribute has different thresholds for different dump trucks. This is due to the maximum load capacity. You may want to turn this parameter into a binary characteristic: 0-empty when weight < 5; 1-loaded when weight > 5. or exclude it altogether.
5. Define the independent variables that you want to train the neural network on.
6. Save the independent variables to a separate "inputs" file, and the values of the speed variable to a separate "target" file.
7. Import files to any of the instrumental computing environments that support the ability to train artificial neural networks: Matlab, Statistica, Deductor, etc.Or use libraries for Python. 
8. Set the neural network structure with the following parameters:
- direct propagation network (perceptron) for linear regression;
- your number of neurons in the input layer, equal to the number of attributes in the inputs file;
- one hidden layer of neurons with a logistic activation function and the number of neurons equal to+1 to the number of neurons in the input layer;
- one neuron in the output layer-target (speed attribute);
- initial sample split: 70% for training, 15% for validation, 15% for testing;
- the maximum number of training epochs is 1000;
- auxiliary stop criterion - growth of the root-mean-square error.
9. Conduct initial network training and evaluate the results. Try changing the training settings in accordance with the guidelines in order to improve the accuracy of the model (minimize the root-mean-square error). 


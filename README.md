# Veggie-distributor
### Mathematical model of a device that allows to distribute vegetables by weight
##### This device is an 8-sector cylinder with dividing plates. We fill it with 2 layers of vegetables, plates rise up and divide vegetables by sectors. My goal is to test a hypothesis that says the weight of vegetables in sectors will be almost the same. For example, if we have 24 kg of potato in cylinder the weight in each sector will be 8 (+- epsilon) kg. It's almost impossible to test this theory in real life, so I've decided to make a mathematical model of this device. 
##### In order to facilitate the model I use 2-D space, as if viewed from above on a cylinder. Vegetable is an ellipse with fixed ratio between large and small axis, mass of vegetable is normally distributed and there's ratio between mass and big axis.
### Input Data
##### Radius of cylinder base (circle), total weight of vegetables, ratios, mean and standard deviation of normal distribution.
### Output Data
##### Vegetables' weight in each sector
### Programming Language
##### Python
### First Approach
##### The first step is to fill cylinder base (circle) with ellipses so that free space in circle was as little as possible.



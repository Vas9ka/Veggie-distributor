# Veggie-distributor
### Mathematical model of a device that allows to distribute vegetables by weight
 This device is an 8-sector cylinder with dividing plates. We fill it with 2 layers of vegetables, plates rise up and divide vegetables by sectors. My goal is to test a hypothesis that says the weight of vegetables in sectors will be almost the same. For example, if we have 24 kg of potato in cylinder the weight in each sector will be 8 (+- <img src="https://tex.s2cms.ru/svg/%5Cepsilon" alt="\epsilon" />) kg. It's almost impossible to test this theory in real life, so I've decided to make a mathematical model of this device. 
 In order to facilitate the model I use 2-D space, as if viewed from above on a cylinder. Vegetable is an ellipse with fixed ratio between large and small axis, mass of vegetable is normally distributed and there's ratio between mass and big axis.
### Input data
Radius of cylinder base (circle), total weight of vegetables, ratios, mean and standard deviation of normal distribution.
### Output data
 Vegetables' weight in each sector
### Programming language
 Python
### Plan
* The first step is to fill cylinder base (circle) with ellipses so that free space in circle was as little as possible.
* Secondly, fill the second layer with maximum number of ellipses
* Thirdly, divide circle into 8 equal parts
* Finally, find weight of ellipses in each sector
### First approach
The main problem of first step is to find optimal distribution of ellipses in circle. Firstly, I tried to put the first ellipse into the left bottom of circle and put following ellipses with x axis offset. If center of next ellipse (x,y) is (<img src="https://tex.s2cms.ru/svg/%20x%5E2%20%2B%20y%5E2%20%3E%20r%5E2%20" alt=" x^2 + y^2 &gt; r^2 " />) then move up y on first ellipse height and put x to the left side of circle. Repeat to all ellipses. This algorithm works fine if standard deviation isn't very big. For example, if <img src="https://tex.s2cms.ru/svg/%20%5Cmu%20%3D%20120%2C%20%5Csigma%20%3D%2010%3A" alt=" \mu = 120, \sigma = 10:" />

![small standard deviation](https://user-images.githubusercontent.com/31739813/66956141-8d580180-f06c-11e9-8115-da665a83124d.jpg)

But if <img src="https://tex.s2cms.ru/svg/%20%5Cmu%20%3D%20120%2C%5Csigma%20%3D%2050%3A" alt=" \mu = 120,\sigma = 50:" />

![big standard deviation](https://user-images.githubusercontent.com/31739813/66956201-a8c30c80-f06c-11e9-824c-ad11fbff71bf.jpg)

So I've decided to change algorithm. Firstly, I've sorted all ellipses in ascending order by size and tried the algorithm I'd used before . The results got better:

![good result](https://user-images.githubusercontent.com/31739813/66956242-baa4af80-f06c-11e9-91af-5d6634f39d2a.jpg)

But distribution still can be optimized. 

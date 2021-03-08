
# Citation
Liu, Changliu, et al. "Improving efficiency of autonomous vehicles by V2V communication." 2018 Annual American Control Conference (ACC). IEEE, 2018.

# Abstract

The corporative adaptive cruise control (CACC), which could minimize inter-vehicle distance and increase platoon density. Based on the V2V communication, Liu introduced a distributed method for intersection management by requiring vehicles to exchange information of their intentions, and then the algorithm will decide the dependencies between vehicles, and arrange the passing sequence by solving their topological graphs. 

Also, to resolve the deadlock among multi vehicle passing sequence, because it would be possible that all vehicle would like to yield to others. To break this tie, Liu assigned a priority score when a deadlock is detected.

# Spotlight

From the single vehicle perspective, how to build a cost function of a single vehicle: the goal for each vehicle is to minimize the cost function, containing run-time cost and terminal cost.

From system level, the cost function is the weighted mean of the cost function sent by each single vehicle.

If there are vehicles which are not connected with the current vehicle, then the current vehicle needs to slow down in order to avoid the conflict zone. (it sounds weired, which means the car without fancy equipments and communication tools should always go first? then why people want to buy fancy cars, given they need to yield to these cars)

# What to learn 

1. Since she didn't give the details of the cost function, what is that? how to properly build a cost function?

2. K. C. Dey, L. Yan, X. Wang, Y. Wang, H. Shen, M. Chowdhury, L. Yu, C. Qiu, and V. Soundararaj, “A review of communication, driver characteristics, and controls aspects of cooperative adaptive cruise control (CACC),” IEEE Transactions on Intelligent Transportation Systems, vol. 17, no. 2, pp. 491–509, 2016.
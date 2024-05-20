# CFU-Pickr
For colony picking with large DNA libraries, This repository contains files for simulating colony picking off of agar plates that could contain libraries of DNA (mulitple unique DNA constructs). Transforming entire libaries at once into a single plate allows for higher throughput work. A problem arises with this stratedgy however. Transforming in this way could present bias in colonies present on the plate; even if no bias is present, more colonies would likely need to be picked than otherwise necessary to ensure at least one copy of each construct be picked. Picking more colonies ensures a complete library but also increases cost. Thus, an optimal least amount of picks is required to reduce cost and keep throughput high.

To do this, the CFU-Pickr was created. This notebook allows a user to optomize the number of picks off an agar plate to ensure picking a full library with the min number of total picked colonies. The notebook takes an image of an agar plate as input. An imaging algorithm is used to count the total pickable CFUs on the plate. This information is then passed through a series of functions that calculate the min number of Colonies required to be picked based on the following user inputs:

            1) Total Unique DNA constructs (DNA lib. size)
            
            2) Confidence Interval = from 0 up to 1.0
            
            3) Number of picking trials to simulate

How it works:
* Using the number of total colonies on plate, a virtual plate is created where the unique DNA constructs are distributed as equally as possible among the total amount of CFUs.
* Colony Picking is then simulated based on the virtual plate. Colony picking continues until the entire DNA library is completely picked.
* Colony Picking is re-simulated from the beginning for a total of N trials
* The results of each trail (the number of picks it took to reach a complete lib.) is used to generate a normalized histogram (distribution) plotting the number of picks each simulation took, and the number of times that type of simulation event was reached.
* Using the generated distribution, a user can select a confidence interval X to determine the least number of picks required to obtain a full library with X% certainty.

Outputs:
* Distribution graphic
* Imaged plate with Colonies selected shown
* Optimal amount of colonies to pick

            

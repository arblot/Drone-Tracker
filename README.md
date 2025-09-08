# Drone-Tracker

Part of the winning project for the Helsing Acoustic Challenge at EDTH Copenhagen

My part of the project consisted on simulating how sound is propagated in 3D, then using this to track down enemy drones using Time Difference of Arrival (TDOA).
We start by taking a sound in a .wav file, which should be located in the same folder as the .ipynb. Then, the program will take 4 points in 3D coordinates, and it will create 4 .wav audio files -one for each point- of how the sound will arrive at that point. Mainly we focused on sound decay at each position, as well as the time-shift due to the difference in distance in relation to the emitter.

Once we were able to simulate the time-shifts, we used cross-correlation between the audio files to know the time-shifts they had with respect to each other. Knowing the time differences then allows us to use the TDOA method to probabilistically track down the drone that is producing the sound.

Plans for future work: 
1. Adding different noise to each of the 4 audio receivers: This will make it more complicated for the probabilistic prediction of the drone position, as the cross-correlation of the sounds will not yield results that are as clean as the ones we have now.
2. Using the previous drone movements to make predictions of where it will go: These drones move at speeds of close to 200km/h, meaning 1/5th of the speed of sound. This means that by the time we receive the sound, that drone has potentially moved 1/5th of the distance between the receiver and the drone. So analysing past movements to see where it will go is crucial, as the position that our tracker indicates is always delayed in comparsion to the real position.

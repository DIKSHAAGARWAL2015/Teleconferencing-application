# Teleconferencing-application
Matlab not suppporting audio device. Need to debug.
20kHz sampling frequency.
1.	Consider a microphone array. (Considered a 4 micro phone array, square is the use case)
2.	Consider speaker source at SX, SY (typically inside square). This is ground truth value.
3.	Compute transit time to each microphone (4 values). Using Euclidean distance formulae.
4.	Generate a sound signal sampled at 20 ksamples/sec i.e. (0.25 s) for example approx. 20 pts)
5.	Create associated time vector to correspond to sampling times
6.	Add delay to the four sound signals using circshift in MATLAB. Basically, the delay will be added as number of points shifted. To calculate the number of points to shift we do (transit time calculated in Step 3)/ time interval. Here time interval is 1/sampling freq.
7.	Now we will use xcorr function in MATLAB.
8.	After doing co-relation we will have the number of points each signal is shifted with respect to each other. So, we can calculate delay using (number of points) * time interval.
9.	Now, basically we know time difference of arrival. So, it will be a hyperbola trajectory. So, we can calculate the estimated source location.
10.	After finding estimated source location we can calculate the error with ground truth value.
11.	 I have attached a video demo.

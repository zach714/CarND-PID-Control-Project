# CarND-Controls-PID
Self-Driving Car Engineer Nanodegree Program

---	

###Describe the effect of the P, I, D component of the PID algorithm in their implementation. Is it what you expected?

The P, I, and D errors did effect the controller as expected. I chose the following gains for my controller:
    
Kp = 0.2

Ki = 0.004

Kd = 3.0

p_error is error that is proportional to the cross track error (cte). 
In this case, p_error = Kp * cte. If Kp is too high, the system may become unstable, but if it is too low the system may not act quickly enough to overcome the error.

i_error is the error proportional to the magnitude and duration of cte where i_error = Ki * accumulated sum of all cte's.
i_error allows the system to overcome any biases that may exist such as an out of aligned steering.

d_error is equal to Kd * the change in cte, and it is used to apply counter-steer as the cte becomes smaller to reduce the magnitude of the overshoot due to p_error.
This will reduce the settle time and stability of the controller

###Describe how the final hyperparameters were chosen.

The hyperparameters were chosen manually via trial and error starting with the parameters used in the lessons (Kp = 0.2, Ki = 0.004, Kd = 3.0).
After various tweaks, I found that these parameters worked out really well throughout the track and stayed with them.

I attempted to implement a twiddle at first, but was having difficulty getting it to run with the simulator correctly, but I hope to be able to get it working once this term is over.
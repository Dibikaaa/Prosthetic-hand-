# Prosthetic-hand-

Prosthetic Hand DC Motor - PID Tuning SimulationControl Systems Project | EEE

Simulated and tuned a DC motor for a prosthetic finger to achieve smooth, jerk-free grip.
PID tuned DC motor simulation for prosthetic hand finger control. Achieved critically damped response (Kp=10, 0% overshoot) for smooth, jerk-free grip using Python Control library.


Motor Parameters
- J = 0.01 kg.m² (Rotor Inertia)
- b = 0.1 Nms (Damping)
- K = 0.01 (Torque Constant)
- R = 1 Ohm, L = 0.5 H

Transfer Function derived:
`TF = K / ( (J*s + b)*(L*s + R) + K² ) = 0.01 / (0.005s² + 0.06s + 0.1001)`

What I did
1.  Simulated step response without PID - showed DC gain only 0.099, insufficient for grip.
2.  Designed PID controller: `PID = (Kd*s² + Kp*s + Ki) / s` with Kd=0.1, Ki=5
3.  Tuned Kp = [1, 10, 30] to find optimal damping.

Results
- **No PID:** Overdamped, ~0.15 speed
- **Kp=1:** Slow rise
- **Kp=10:** CRITICALLY DAMPED (BEST) - 0% overshoot, smooth grip, ideal for prosthetic
- **Kp=30:** Fast but slight overshoot - causes jerky movement, not safe

Viva Values:
Kp=1  -> Overshoot=0.00%, Settling=6.35s
Kp=10 -> Overshoot=0.00%, Settling=11.86s
Kp=30 -> Overshoot=0.00%, Settling=19.52s

Tech Stack
Python, Control Systems Library, Matplotlib, Google Colab

How to Run
pip install control
python prosthetic_pid.py

Application
This tuning ensures prosthetic hand grips objects without dropping or crushing - critical for real-world assistive devices.



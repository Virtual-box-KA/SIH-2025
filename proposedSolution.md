# Proposed Solution

Solution - We will take the multi-source data input. Process the data, and predict any possible outcome for rockfall. If there is any possibility of rockfall, we will mark that zone as a Red Zone. Other areas will be marked accordingly. A web dashboard for the site engineer to monitor everything. A real-time risk map will be provided in the dashboard for the engineer to see and plan beforehand. We want to opt for the `low-cost monitoring hardware` to enable real-time monitoring and provide real-time updates to the engineer. A mobile app for the supervisors or the miners. Providing real-time alerts to them and also providing them an evacuation plan to reach a safer spot. 

We are dividing the problem statement into 4 parts as follows:

1. Machine Learning Model
2. Web Dashboard
3. Mobile Application
4. Monitoring hardware (optional, but we will try to implement it)

---

## Machine Learning Model

As the problem statement describes, `multi-source data inputs` we need to use multiple models.

  1. Drone-captured imagery – We propose to use `OpenCV/TensorFlow` it to compare it with the previous set of data and find if there is any anomaly detection.<br>
     a. We will use CV2 to detect any visual changes in the frame (less ML-heavy model).
     b. CV2 will also be used to print a contour map of the same data. If any anomaly is found, it can be detected.

  2. Environmental factors (rainfall, temperature, vibrations) – We propose to use `regression`, to predict any possible movement of the rock. If yes, how much will it move? Before it actually falls.

  3. Geotechnical sensor data (displacement, strain, pore pressure) – Similar to the 3rd point, `regression` can be used here as well.

  4. Digital Elevation Models (DEM) – DEMs (simpler) can be used in Python. Any anomaly can be detected directly. If we go for complex data, we propose to use CNN.

### All these models can be used individually to implement and present data more precisely and well structured.


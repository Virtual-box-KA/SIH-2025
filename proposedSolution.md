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

  2. Environmental factors (rainfall, temperature, vibrations) – We propose to use `regression`, to predict any possible movement of the rock. If yes, how much
     will it move? Before it actually falls.

  4. Geotechnical sensor data (displacement, strain, pore pressure) – Similar to the 3rd point, `regression` can be used here as well.

  5. Digital Elevation Models (DEM) – DEMs (simpler) can be used in Python. Any anomaly can be detected directly. If we go for complex data, we propose to use CNN/
     GDAL (Geospatial Data Abstraction Library): A powerful library to read, write, and process raster and vector geospatial data, including DEMs.

  6. Edge computing - Efficiently processing data near the source of data generation (e.g., sensors, drones) rather than sending it all to a centralized cloud.
     This enables faster analysis, reduces latency, and lowers bandwidth use, which is crucial for real-time anomaly detection in mining environments.

### All these models can be used individually to implement and present data more precisely and well structured.

## Mobile Application

This project introduces an AI-driven rockfall prediction system integrated with an Android application for visualization, alerts, and decision-making.

    The app provides
     1) Real-time risk maps
     2) Probability-based forecasts
     3) Instant alerts (SMS/Email/Push)
     4) Reports for decision support

  ### Objectives
     1) Predict potential rockfall incidents using multi-source data.
     2) Enable real-time alerts for proactive safety measures.

  ### Android App Features
        1) Authentication:
            Secure login/signup
            Role-based access
            
        2) Dashboard:
          Current rockfall risk level (Low/Medium/High)
          Latest alerts summary

        3) Risk Map:
            Interactive GIS-based heatmap
            Color-coded vulnerability zones
            Tap to view probability % and sensor readings

        4) Sensor Data:
            Real-time graphs of:
                Displacement
                Strain
                Pore pressure
                Rainfall & Temperature
            Custom time filtering (24h, 7 days, monthly)

        5) Alerts & Notifications:
            In-app, SMS, and Email alerts
            Timestamp + location details
            Recommended action plans
            Recommended action plans

        6) Settings:
            Profile management
            Profile management
        

# Proposed Solution

We are dividing the Problem Statement in 4 parts as -
1. Machine Learning Model
2. Web Dashboard
3. Mobile Application
4. Monitoring hardware (Optional, but we will try to implement it)

---
**Machine Learning Model**
As the problem statement describes, `multi-source data inputs` we need to use multiple models
  1. Drone-captured imagery - We will use `OpenCV/TensorFlow` to compare it with the previous set of data and find if there is any anamoly. We should be worried of.
     a. We will use CV2 to detect any visual changes using pixel
  3. Environmental factors (rainfall, temperature, vibrations) - We propose to use `regression`, to predict any possible outcome, from the given data.
  4. 

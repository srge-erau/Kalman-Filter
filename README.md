# An Introduction to the Kalman Filter: Presentation and Code

> We created this for our lab at Embry-Riddle Aeronautical University, the Space Robotics and Generative Estimation (SRGE) Lab. The theoretical content is largely based on the book *Optimal State Estimation: Kalman, H-infinity, and Nonlinear Approaches* by Dan Simon. Any errors are our own, and all content is for educational purposes and may contain errors. Please verify any critical information before use.

Welcome to this repository for "An Introduction to the Kalman Filter." This collection of materials is designed to provide a comprehensive overview of Kalman filtering, from the foundational concepts of least-squares estimation to advanced nonlinear applications in robotics.

This repository is perfect for undergraduate students, researchers, or anyone interested in learning about one of the most fundamental algorithms in robotics and control systems.

## 📁 Repository Structure

* **/Kalman_Filters_v0_1.pdf**: Contains the full lecture presentation in PDF format.
* **/code**: Includes Python code examples that correspond to the "Code Review" sections of the presentation. These examples provide practical implementations of the concepts discussed.

## 📖 Presentation Overview

The presentation is a deep dive into the theory and application of Kalman filters. It is structured to build knowledge from the ground up, making complex topics accessible.

### Key Topics Covered:

* **Fundamentals of State Estimation**
    * **Least-Squares Estimation**: The presentation starts by framing state estimation as an optimization problem, introducing the batch least-squares method for estimating a constant value from noisy measurements.
    * **Weighted Least-Squares (WLS)**: It extends the concept to account for varying sensor quality by introducing the measurement covariance matrix, **R**.
    * **Recursive Least-Squares (RLS)**: The inefficiency of batch processing is addressed by deriving the RLS algorithm, an online method to update estimates with new data efficiently.

* **The Linear Kalman Filter**
    * **Dynamic Systems**: The limitation of a "constant state" assumption is lifted by introducing a state-space model for dynamic systems, including the state transition matrix (**F**) and process noise (**Q**).
    * **The Predict-Update Cycle**: The core of the Kalman filter is presented as a two-step cycle: predicting the next state and then correcting it with a measurement. The derivation combines the dynamic propagation model with the RLS measurement update.
    * **Optimality**: The presentation explains why the Kalman filter is considered the **Best Linear Unbiased Estimator (BLUE)** under certain conditions.

* **Nonlinear Kalman Filters**
    * **Extended Kalman Filter (EKF)**: For nonlinear systems, the EKF is introduced as the industry standard. It handles nonlinearity by linearizing the system model at each time step using **Jacobians**.
    * **Error-State Kalman Filter (ESKF)**: An advanced and often more stable variation that estimates the *error* in the state rather than the state itself. This method offers superior linearization and is particularly effective for systems involving 3D rotations.
    * **Unscented Kalman Filter (UKF)**: An alternative to the EKF that avoids Jacobians by propagating a set of "sigma points" through the true nonlinear model, often resulting in higher accuracy.
    * **Particle Filter**: A brief introduction to this non-parametric, brute-force method used for highly nonlinear systems, popular in ROS applications like AMCL and GMapping.

## 💻 Code Examples

The code provided in the `/code` directory is designed to be a practical companion to the presentation.

* **Code Review 1: Batch vs. Recursive Least Squares**: A simple 1D example demonstrating how the RLS estimator efficiently converges to the true value, just like the batch method, but without needing to reprocess all past data.
* **Code Review 2: Linear Kalman Filter**: A 1D tracking problem (e.g., tracking a cart's position and velocity) to illustrate the predict-update cycle of the linear KF in action.
* **Code Review 3: Linear KF on Nonlinear Data**: Highlights the limitations of a linear filter by applying it to a 2D nonlinear motion model, showing how model mismatch leads to poor performance.
* **Code Review 4: Extended Kalman Filter (EKF)**: A 2D vehicle navigation example where the EKF is used to track position, speed, and heading based on a nonlinear motion model.
* **Code Review 5: Sensor Fusion (IMU & GPS)**: A practical robotics example of fusing high-frequency IMU data (for propagation) with low-frequency GPS data (for correction) to achieve a robust and drift-free state estimate for a rover.

## 🚀 How to Use

1.  **Download the Presentation**: The `Kalman_Filters_v0_1.pdf` file.
2.  **Explore the Code**: The Jupyter Notebooks in the `/code` directory are standalone examples. You can run them to see the filters in action. Ensure you have standard Python libraries like `numpy` and `matplotlib` installed.

    ```bash
    pip install numpy matplotlib
    ```

## 🤝 Contributing

Contributions are welcome! If you find any errors, have suggestions for improvements, or want to add more examples, please feel free to:

* Open an issue to report bugs or suggest features.
* Fork the repository and submit a pull request with your changes.

## 📜 License

This work is licensed under the [MIT License](LICENSE). You are free to use, share, and adapt the materials, but please provide attribution.

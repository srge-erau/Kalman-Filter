# An Introduction to the Kalman Filter

Lecture slides and executable notebooks for learning state estimation, from least squares through nonlinear filtering and IMU/GPS sensor fusion. The materials were created for the Space Robotics and Generative Estimation (SRGE) Lab at Embry-Riddle Aeronautical University.

> The theoretical presentation draws primarily from Dan Simon's *Optimal State Estimation*. These materials are educational and may contain errors; independently verify critical applications.

## Topics

- Batch, weighted, and recursive least squares
- Linear state-space models and the Kalman predict/update cycle
- Model mismatch on nonlinear systems
- Extended and error-state Kalman filter concepts
- Unscented and particle filter introductions
- IMU propagation with lower-rate GPS corrections

## Repository contents

| Path | Description |
| --- | --- |
| `Kalman_Filter.pdf` | Full lecture presentation |
| `code/1_least_square.ipynb` | Batch versus recursive least squares |
| `code/2_linear_KF.ipynb` | Linear Kalman filter for 1D tracking |
| `code/3_nonlinear_data_kalman_filter.ipynb` | Linear filtering with nonlinear data |
| `code/4_EKF.ipynb` | Extended Kalman filter for 2D navigation |
| `code/5_imu_gps.ipynb` | IMU/GPS sensor-fusion example |
| `code/state_propagation.ipynb` | Supplemental motion-propagation notebook |

## Quick start

```bash
git clone https://github.com/srge-erau/Kalman-Filter.git
cd Kalman-Filter
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
jupyter lab
```

Open `code/1_least_square.ipynb` and continue through the numbered notebooks. Each notebook is designed to be run from a clean kernel.

## Reproducibility tips

- Restart the kernel and run all cells before sharing a result.
- Record any random-seed, parameter, or noise-setting changes.
- Treat generated trajectories as demonstrations, not calibrated sensor datasets.
- Use the presentation alongside the notebooks for definitions and derivations.

## License

No license file is currently included. Unless a license is added, normal copyright restrictions apply; contact the maintainers before redistributing or adapting the materials.

## Maintainer

[Space Robotics and Generative Estimation (SRGE) Lab](https://github.com/srge-erau), Embry-Riddle Aeronautical University.

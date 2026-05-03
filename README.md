# solar-array-articulation

Vision-based control algorithm for dual-axis solar array articulation

## Setup

- Clone the repository
  ```bash
  git clone git@github.com:derekc22/solar-array-articulation.git
  cd solar-array-articulation
  ```

- Create virtual environment
  ```bash
  python3 -m venv venv
  source venv/bin/activate
  ```

- Install dependencies
  ```bash
  pip install opencv-python numpy matplotlib picamera2 RPi.GPIO Pillow
  ```

- Create output directories
  ```bash
  mkdir -p data photos
  ```

- Enable the Raspberry Pi camera
  ```bash
  sudo raspi-config
  ```

## Hardware

- Raspberry Pi 4
- Raspberry Pi Camera Module
- 2 servo motors for pitch control
- 2 stepper motors for yaw control
- 2 stepper drivers with PUL, DIR, and ENA inputs
- 2 limit switches for homing
- External motor power supply
- Solar panel mounting hardware

## GPIO

### Panel 1
- Servo: Pin 40
- Stepper PUL: Pin 35
- Stepper DIR: Pin 37
- Stepper ENA: Pin 38
- Limit switch: Pin 11

### Panel 2
- Servo: Pin 3
- Stepper PUL: Pin 10
- Stepper DIR: Pin 12
- Stepper ENA: Pin 8
- Limit switch: Pin 13

## Usage

- Run the main tracking script
  ```bash
  source venv/bin/activate
  python articulate.py
  ```

- Press spacebar to stop tracking and return to home position

## Tests

- Test camera
  ```bash
  python testcam.py
  ```

- Test servos
  ```bash
  python servo.py
  ```

- Test steppers
  ```bash
  python stepper.py
  ```

## Output

- Motor position logs are written to CSV files:
  - `servo1_coords.csv`
  - `stepper1_coords.csv`
  - `servo2_coords.csv`
  - `stepper2_coords.csv`

- Plots are saved as:
  - `*_coords_plt.pdf`

- Captured images are saved in:
  - `photos/`

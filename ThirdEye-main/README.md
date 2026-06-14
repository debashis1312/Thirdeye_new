# ThirdEye

ThirdEye is an experimental driver safety system that detects driver drowsiness using real-time facial monitoring and can trigger an alarm and an Arduino-controlled braking mechanism to reduce accident risk.

**Key features**
- **Real-time drowsiness detection:** Eye-closure and facial monitoring using Python and dlib.
- **Alarm:** Audible alert when the driver shows signs of fatigue.
- **Automatic braking (hardware):** Optional Arduino-controlled actuator to apply brakes if the driver remains unresponsive.

**Patent:** This project is [patent-pending](https://drive.google.com/file/d/1FRE9teJaQ9bo7Q4lqErc0LPI0UjavT3H/view).

**Technologies:** Python, OpenCV (`cv2`), NumPy, dlib, imutils, Arduino (Uno).

**Table of contents**
- Quick start
- Requirements
- Installation
- Usage
- Hardware setup
- Project files
- License

## Quick start
1. Clone the repository (or download and open in your workspace).
2. Install Python dependencies (see below).
3. Connect the camera and Arduino hardware per the Hardware setup section.
4. Run the detection script:

```powershell
python drowsinessDetector@deva.py
```

## Requirements
- Python 3.8+ (3.10 recommended)
- pip
- A camera accessible by OpenCV
- Arduino Uno (for hardware braking integration)

Python libraries used:
- `opencv-python` (`cv2`)
- `numpy`
- `dlib`
- `imutils`
- `face_utils` (from `imutils`/`opencv-contrib` helper)

Create a `requirements.txt` if you'd like reproducible installs.

## Installation
Install required Python packages:

```powershell
pip install opencv-python numpy dlib imutils
```

Notes: Installing `dlib` may require CMake and a suitable C++ compiler on Windows.

## Usage
- Verify your camera index (0 is usually the default).
- Run the script shown in Quick start. The script will open a camera window and monitor eye aspect ratio to detect drowsiness. When drowsiness is detected, it triggers an alarm and, after a configured timeout, signals the Arduino for braking.

## Hardware setup
- Connect the camera to the host running the Python script.
- Connect Arduino Uno via USB to the host. The Arduino sketch (`sketch_nov24a.ino`) contains the actuator/brake-control logic. Ensure serial baud rates match in the Python script and the sketch.

## Project files
- `drowsinessDetector@deva.py`: Main detection script.
- `sketch_nov24a.ino`: Arduino sketch for braking/actuator control.
- `shape_predictor_68_face_landmarks.dat`: dlib facial landmarks model (large file).
- `LICENSE`, `CODE_OF_CONDUCT.md`, `README.md`

## Security & privacy
- This project processes camera images locally. Do not publish or transmit recorded video feeds without informed consent.

## Contributing
Feel free to open issues or pull requests on GitHub. For substantial contributions, please include tests and documentation.

## License
This repository includes a `LICENSE` file. See the license terms in that file.

---

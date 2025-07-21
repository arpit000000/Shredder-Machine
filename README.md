# 🧠 Shredder Machine – Hand Detection & Safety Monitoring System

A computer vision-based safety monitoring system that detects hands near a shredder machine using real-time webcam input. It uses object detection with TensorFlow and tracks hand movement to count detections and safety line violations.

---

## 📌 Features

- ✋ Real-time **hand detection**
- ⚠️ Tracks when a hand crosses safety and machine zones
- 📈 Logs daily stats in an Excel file
- 📹 Live video processing using `OpenCV` and `imutils`
- 🧠 TensorFlow object detection API for hand detection
- 💾 Auto-saving results to `result.xls` (including date-wise data)

---

## 📂 Project Structure

├── orien_lines.py # Utility to draw orientation lines
├── detector_utils.py # Detection helper using TensorFlow
├── main.py # Main script to run the detection and logging
├── result.xls # Output file storing detection history
├── requirements.txt # Python package requirements
└── README.md # Project documentation

---

## 🛠️ Installation

### 1. Clone the Repository

```bash
git clone https://github.com/arpit000000/Shredder-Machine.git
cd Shredder-Machine
2. Create and Activate a Virtual Environment (Optional)
python -m venv venv
source venv/bin/activate        # macOS/Linux
venv\Scripts\activate           # Windows
3. Install Dependencies

pip install -r requirements.txt
▶️ How to Run
python main.py
The script starts your webcam and detects hand presence in real-time.

It draws machine and safety lines.

On pressing q, the detection stops and logs are saved to result.xls.

🧪 Tech Stack
TensorFlow 1.14 + Object Detection API

OpenCV for video stream handling

Pandas, xlrd, xlwt, xlutils for Excel data logging

imutils for camera stream

Python 3.x

📊 Excel Output
After each session, data is appended to an Excel file result.xls:

Sl. No	Date	Number of times hand detected	Number of times hand crossed
1	2025-07-20	12	5
...	...	...	...

⚙️ Configuration
You can modify the following in main.py:

Orientation = 'bt' – orientation of motion (e.g., lr, rl, bt, tb)

Line_Perc1 = 15 – position for the machine line

Line_Perc2 = 30 – position for the safety line

score_thresh = 0.80 – confidence threshold for detection

🚧 Limitations
Uses TensorFlow 1.x which is older; can be upgraded to TF 2.x with effort

Works best in well-lit environments

Requires webcam and a decent CPU/GPU for real-time performance

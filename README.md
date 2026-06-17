# 🏀 Basketball Shot Analyzer

A computer vision and machine learning project that analyzes basketball shots from video and predicts whether a shot will be made or missed in real time.

## 🚀 Features

* Detects basketballs using **YOLOv11**
* Tracks ball position frame-by-frame
* Calculates motion features:

  * Position `(x, y)`
  * Velocity `(vx, vy)`
  * Speed
  * Distance from rim
* Logs shot data into a CSV dataset
* Uses a **PyTorch neural network** to predict shot success
* Displays predictions in real time on video

## 🧠 How It Works

### 1. Object Detection

Uses YOLOv11 to detect the basketball in each frame.

### 2. Tracking & Physics

Computes:

* Δx, Δy
* Velocity `(vx, vy)`
* Speed
* Distance to rim

Tracks the ball trajectory throughout the shot.

### 3. Data Collection

Stores frame-by-frame shot data in:

```bash
Final_Shots.csv
```

### 4. Machine Learning

Trains a PyTorch neural network on collected shot data and outputs the probability that a shot will be made.

## 📂 Project Structure

```text
Basketball-Shot-Analyzer/
│
├── main.py                # YOLO + OpenCV tracking
├── model.py               # PyTorch model
├── Final_Shots.csv        # Dataset
├── videos/                # Input videos
└── README.md
```

## 🛠️ Tech Stack

* Python
* OpenCV
* Ultralytics YOLOv11
* PyTorch
* NumPy
* Pandas

## ⚙️ Installation

```bash
pip install ultralytics opencv-python torch pandas numpy
```

## ▶️ Usage

### Place your video file

```text
vid.mp4
```

### Run detection and tracking

```bash
python main.py
```

### Train the prediction model

```bash
python model.py
```

## 📊 Example Features (CSV)

| frame | ball_x | ball_y | vx | vy | speed | label |
| ----- | ------ | ------ | -- | -- | ----- | ----- |
| 12    | 320    | 210    | 5  | -3 | 5.8   | 1     |

* `label = 1` → Shot Made ✅
* `label = 0` → Shot Missed ❌

## 🎥 Demo

![Preview](https://img.youtube.com/vi/B-A5uHzQIgI/0.jpg)

▶️ Full Demo: https://www.youtube.com/watch?v=B-A5uHzQIgI

## 🔮 Future Improvements

* Improve ball detection accuracy
* Use multiple videos for training
* Add trajectory prediction visualization
* Real-time shot feedback system
* Train more advanced models (LSTM / Transformers)

## 💡 Inspiration

This project combines computer vision, physics, and machine learning to simulate how modern basketball analytics systems track and predict shot outcomes.

## 👨‍💻 Author

**Aurick Anwar**

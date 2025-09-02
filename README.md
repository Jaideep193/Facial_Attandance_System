# Facial Attendance System

## Overview
A Python-based Attendance Management System using Face Recognition, leveraging OpenCV and machine learning. This system automatically marks attendance by recognizing faces from a webcam feed and records the results in a CSV file.

## Key Features
- **Face Detection and Dataset Creation:**  
  Capture face images from webcam and organize them in structured datasets per user.
- **Model Training:**  
  Train an LBPH (Local Binary Patterns Histograms) face recognizer on the captured dataset for reliable identification.
- **Real-time Attendance Marking:**  
  Recognize faces in real-time and mark attendance only once per user, per day, directly into `attendance.csv`.
- **Data Persistence:**  
  Stores user-face datasets, trained model weights (`face_recognizer.yml`), and label mappings (`label_map.npy`).

## How It Works
1. **Dataset Creation:**  
   - Use the webcam to capture 50 images per user.
   - Images are stored under `dataset/{name}_{user_id}`.
2. **Model Training:**  
   - Loads all user images.
   - Trains the model and saves weights and label mapping.
3. **Attendance Marking:**  
   - The system detects and recognizes faces in the webcam feed.
   - On successful recognition with adequate confidence, marks the user present in `attendance.csv`, ensuring no duplicate entries for the same day.

## Files
- `Facial_Attendance_System.ipynb`: Main Jupyter Notebook for all functionalities.
- `attendance.csv`: Output file containing attendance records (Name, Date, Time).
- `face_recognizer.yml`: Saved model weights.
- `label_map.npy`: Numpy mapping of user labels.
- `dataset/`: Directory for user face samples.

## Requirements
- Python 3.x
- OpenCV (`cv2`)
- numpy
- pandas

## Usage
Run the Jupyter notebook `Facial_Attendance_System.ipynb` step by step to:
1. Create dataset for new users.
2. Train the face recognition model.
3. Recognize users and mark their attendance.

## Author
- Jaideep193

# 🧑‍💻 Facial Attendance System

## 👀 Overview
A Python-based Attendance Management System using Face Recognition (OpenCV + Machine Learning).
Automatically recognizes faces from a webcam to mark attendance in real-time, saving the results in a CSV file!

---

## ✨ Key Features

- **🖼️ Face Detection & Dataset Creation:**  
  Capture face images from a webcam and organize them into structured user folders.
- **🧑‍🏫 Model Training:**  
  Train a robust LBPH (Local Binary Patterns Histograms) recognizer on your dataset for identification.
- **⚡ Real-time Attendance:**  
  Recognize faces from the live webcam feed and mark attendance only once per user per day (`attendance.csv`).
- **📁 Data Persistence:**  
  All data—including user photos, trained model weights (`face_recognizer.yml`), and label mappings (`label_map.npy`)—is stored for repeated use.

---

## 🔬 How It Works

### 1. 📸 Dataset Creation

- Capture **50 grayscale face samples per user**.
- Images saved in `dataset/{name}_{user_id}/`.

```python
def create_dataset(user_id, name):
    # Uses OpenCV to capture and save 50 face images per user
```
> ![Add a cartoon camera or photos sticker here!](assets/camera_sticker.png)

---

### 2. 🏋️‍♂️ Model Training

- Loads all images from your dataset directory and builds the face recognizer model.
- Trained model saved as `face_recognizer.yml`, with user mapping in `label_map.npy`.

```python
def train_model():
    # Trains the LBPH face recognizer on all dataset images
```
**Console Output Sample:**
```
Loading image from dataset/Jaideep_001/0.jpg
...
Model trained and saved.
```
> ![Medal or progress bar sticker](assets/train_sticker.png)

---

### 3. 🤳 Real-Time Face Recognition & Attendance

- Webcam starts, detects and recognizes faces.
- If recognized, attendance is updated in `attendance.csv` and label appears on-screen.

```python
def recognize_and_mark():
    # Detects and recognizes faces, then writes to attendance CSV
```
**Output Example (attendance.csv):**

| Name        | Date       | Time     |
|-------------|------------|----------|
| Jaideep_001 | 2024-12-10 | 23:12:56 |
| Jaideep_001 | 2024-12-11 | 11:33:47 |

> ![Clipboard or checkmark sticker](assets/attendance_sticker.png)

---

## 📦 Files

- `Facial_Attendance_System.ipynb` – Jupyter notebook with complete workflow.
- `attendance.csv` – Output file: attendance log (Name, Date, Time).
- `face_recognizer.yml` – Trained model weights.
- `label_map.npy` – Numpy mapping for label-to-user.
- `dataset/` – Folder storing all face samples.

---

## ⚙️ Requirements

- Python 3.x
- OpenCV (`cv2`)
- numpy
- pandas

---

## 🚀 Usage

1. Run `Facial_Attendance_System.ipynb`.
2. Execute cells sequentially to:
    - Create a new dataset
    - Train the face recognizer
    - Perform live face recognition & mark attendance

---

## 📸 Sample Outputs

- Live Attendance Example:  
  ![Sample Attendance Screenshot](assets/attendance_sample.png)
  
---

## 👤 Author

**Jaideep193**

(Upload custom sticker images to the `assets/` folder and update their filenames as needed. Emoji and image placeholders make your README visually appealing!)

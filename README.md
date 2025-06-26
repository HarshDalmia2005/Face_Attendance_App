# Face Attendance App

A Python-based face recognition attendance system using OpenCV, Firebase Realtime Database, and Jupyter Notebooks.

## Features

- Collects facial images from a webcam for dataset creation
- Trains a face recognition model using the LBPH algorithm
- Real-time face recognition and attendance marking via webcam
- Stores attendance data in Firebase Realtime Database
- GUI built with Tkinter and CustomTkinter

## Requirements

- Python 3.7+
- OpenCV
- Firebase Admin SDK
- Tkinter, CustomTkinter
- Pillow
- Jupyter Notebook
- Service account JSON key from Firebase

## Setup & Usage

### 1. Firebase Setup

- Create a Firebase Realtime Database project.
- Download the service account key JSON file.
- Place the JSON key in your project directory.

### 2. Collect Face Data

- Run `data_collection.ipynb` to capture grayscale facial images from your webcam.
- Follow the prompt to enter the person’s name (used as the folder name inside `dataset/`).
- The script saves 100 images per person by default.

### 3. Train the Model

- Run `training.ipynb` to train the LBPH face recognizer on your dataset.
- This creates a `face_recognizer.yml` model file and a `label_map.txt`.

### 4. Configure Database

- In your code, update the database URL to your Firebase project URL.
- Set the path to your service account key JSON file.

### 5. Run the Attendance System

- Run `FACE_ATTENDANCE_SYSTEM.ipynb` to launch the GUI.
- The system uses your webcam to recognize faces and automatically mark attendance in Firebase.

### 6. Install Dependencies

Install all required packages before running any code:

```bash
pip install opencv-python firebase-admin pillow customtkinter notebook
```


## Files

| File/Folder                  | Description                                                        |
|------------------------------|--------------------------------------------------------------------|
| `data_collection.ipynb`      | Collects face images for each user using the webcam.               |
| `training.ipynb`             | Trains the LBPH face recognition model on the collected dataset.   |
| `FACE_ATTENDANCE_SYSTEM.ipynb` | Main GUI application for face recognition-based attendance.        |
| `dataset/`                   | Stores images of faces (one subfolder per user).                   |
| `face_recognizer.yml`        | The trained model file generated after training.                   |
| `label_map.txt`              | Maps model labels to person names.                                 |
| `serviceaccountkey.json`     | Firebase service account credentials (must be provided by user).   |
| `background.png`             | Background image used in the GUI (if available).                   |
| `Modes/`                     | Folder containing mode images for GUI display.                     |

## License

This project is licensed under the MIT License.

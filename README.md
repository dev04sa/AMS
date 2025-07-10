
# 🎓 Attendance Management System (AMS) with Facial Recognition

A smart, scalable, and secure Attendance Management System that leverages facial recognition to automate student attendance — eliminating manual errors, proxy attendance, and inefficiencies in academic institutions.

---

## 🚀 Project Overview

The **Attendance Management System (AMS)** is a full-stack solution combining mobile, backend, and machine learning technologies to provide real-time, accurate attendance marking through facial recognition. This system streamlines classroom management for professors and provides transparency for students.

---

## 🎯 Goals & Scope

The system is divided into two key phases:

### 📌 Phase 1: Core Attendance System
- Students mark attendance via **live facial recognition**.
- Professors define a **time window** for attendance submission.

### 📌 Phase 2: Academic Dashboard
- Professors can upload **announcements, notices, and assessments** for students.

---

## 👥 User Roles & Features

### 🧑‍🏫 Professor
- Create classrooms and schedule lectures.
- Define session-based, time-bound attendance windows.
- View attendance logs and student statistics.
- Manually mark attendance in case of recognition issues.

### 👨‍🎓 Student
- Join classroom sessions.
- Mark attendance via facial recognition using the mobile app.
- Track their subject-wise attendance stats.

---

## 💻 Tech Stack

### 🔧 Frontend (Mobile App)
- **Flutter**: Cross-platform development
- **State Management**: Provider & BLoC
- **Firebase SDK**: Auth, Firestore, and Storage

### 🌐 Backend (REST API)
- **Node.js + Express**: API and logic routing
- **MySQL**: Persistent data storage
- **Firebase**: Storage for student images and authentication
- **MariaDB Client**: For MySQL DB integration

### 🤖 Machine Learning
- **TensorFlow + Keras**: Face embedding using MobileNet
- **Flask**: API server for facial recognition
- **MobileNet**: Lightweight and accurate CNN model for feature extraction
- **Face Matching**: Euclidean distance on facial embeddings

---

## 🧠 Facial Recognition – Workflow

1. Student taps **"Mark Attendance"** in app.
2. Camera captures live face image.
3. Image is sent to **Flask server**.
4. Server fetches stored face embeddings from **Firebase**.
5. Embeddings compared using **Euclidean distance**.
6. On match, attendance marked via **Node.js backend** in **MySQL**.

---

## Project Screenshots

![in (3)](https://github.com/user-attachments/assets/5929dcc6-6b65-4c71-a58b-9c996e9eba26)
![in (4)](https://github.com/user-attachments/assets/b14dbff3-02c1-4c28-b9ca-d7cdfdd953f0)
![Home](https://github.com/user-attachments/assets/b5ea519f-fbcb-4bb0-9a11-791f22f04eda)
![Mark_attendance](https://github.com/user-attachments/assets/b7193908-6f88-4074-a59d-3a77592b069a)
![Profile](https://github.com/user-attachments/assets/d32be7f0-ed5e-414b-84a4-883c7f3ce0fa)
![Instant class](https://github.com/user-attachments/assets/8d5c907a-3284-4f5c-a2d6-049cc3c1d0ee)
![Student_details](https://github.com/user-attachments/assets/00574fdf-3702-4f02-bf7e-5fa1552e4383)
![Notification](https://github.com/user-attachments/assets/f495243c-f903-4a6d-8550-d249389167db)
![Home (1)](https://github.com/user-attachments/assets/0bc576e3-feef-4171-9691-180d21ef48c7)
![Mark_attendance (1)](https://github.com/user-attachments/assets/edac7781-f3ad-400f-98b4-1fc2631e9acb)
![Profile (1)](https://github.com/user-attachments/assets/d47fcb82-d38b-4adf-bf5c-94857c548e04)
![Make Attendance 1](https://github.com/user-attachments/assets/dc7f2a8f-2a6b-4ed3-a97b-f386c17da832)
![Make attendance 2](https://github.com/user-attachments/assets/5cf13dd3-488b-45cf-bfab-79ea4457d01b)
![Make Attendance 3](https://github.com/user-attachments/assets/0574e0f0-fb8e-4fc7-8161-0d1133c2a2c6)
![in5](https://github.com/user-attachments/assets/b58d6419-431a-49f7-b64d-c29f41b3ed65)
![in](https://github.com/user-attachments/assets/ce791a06-f8e8-4b38-a1ab-56f2d17a194f)
![in (2)](https://github.com/user-attachments/assets/e642c56a-9433-4b0e-98b1-cd07dcccfcca)


---

## 🗂️ Folder Structure

```bash
📁 lib/
├── core/              # Constants, helpers, error classes
├── features/
│   └── onboarding/
│       └── presentation/
│           ├── pages/
│           ├── widgets/
│           └── bloc/
├── route/             # Navigation config
└── services/          # API calls & Firebase configurations
````

---

## 📦 Dependencies

### Flutter (pubspec.yaml)

```yaml
dependencies:
  flutter:
  firebase_core:
  firebase_auth:
  firebase_storage:
  cloud_firestore:
  provider:
  image_picker:
  table_calendar:
  google_fonts:
```

### Node.js (package.json)

```json
"dependencies": {
  "express": "^4.19.2",
  "body-parser": "^1.20.2",
  "dotenv": "^16.4.5",
  "mariadb": "^3.3.0",
  "nodemon": "^3.1.0"
}
```

---

## 🛠️ Installation & Setup

### ✅ Prerequisites

* Node.js & npm
* Flutter SDK
* Firebase Project (Firestore + Storage)
* Python (for Flask + ML server)

---

## ⚙️ Installation Steps

### 🔹 Backend

```bash
cd Backend
npm install
npm run dev
```

### 🔹 Frontend (Flutter App)

```bash
cd ams_flutter
flutter pub get
flutter run
```

### 🔹 ML Server (Facial Recognition)

```bash
cd face_recognition_server
pip install -r requirements.txt
python app.py
```

---

## 📱 Usage Flow

### 👩‍🏫 Professor

1. Login → Create Class → Schedule Lecture
2. Define Attendance Time Window
3. View/Update Attendance Logs

### 👨‍🎓 Student

1. Login → Join Class
2. Tap “Mark Attendance” → Camera Opens
3. Face Captured → Sent to Server
4. If matched → Attendance Recorded
5. Stats Visible in Dashboard

---

## 🌐 API Endpoints (Node.js)

| Route         | Description            |
| ------------- | ---------------------- |
| `/admin`      | Admin functionalities  |
| `/user`       | Auth & registration    |
| `/student`    | Student data endpoints |
| `/classroom`  | Class management       |
| `/attendance` | Attendance CRUD APIs   |

---

## 📊 Database Schema (MySQL)

### Tables:

* `users (id, name, role, email, passwordHash)`
* `students (userId, classId, imageURL)`
* `classrooms (id, subject, professorId)`
* `attendance (id, studentId, classId, timestamp, status)`

---

## 📌 Future Improvements

* OTP verification for manual overrides
* Push notifications for session reminders
* Admin panel for institution-wide reporting
* Liveness detection to prevent spoofing

---

## 🤝 Contributing

Contributions are welcome! If you’d like to fix a bug or propose a feature, feel free to fork the repo and submit a PR.

---

## 📃 License

MIT License. See [LICENSE](./LICENSE) for details.

---

## 🙋‍♂️ Author

**Dev \[Your Name]**
💼 [LinkedIn](https://linkedin.com/in/yourprofile)
📧 [your.email@example.com](mailto:your.email@example.com)



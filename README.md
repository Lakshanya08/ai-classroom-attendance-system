

# 🤖 AI-Based Classroom Attendance System

An AI-powered web-based attendance management system that uses **face recognition** to identify registered students and automatically record classroom attendance.

---

## 📌 Project Overview

The **AI-Based Classroom Attendance System** is a web application developed using **Python and Flask**.

The system uses a webcam to capture student faces, compares them with registered face data, and automatically records attendance.

It helps reduce manual attendance work and provides teachers with an easy way to manage, monitor, correct, and export attendance records.

---

## 🎯 Objectives

The main objectives of this project are:

* To automate the classroom attendance process.
* To reduce manual attendance work.
* To identify students using face recognition.
* To record attendance automatically.
* To store student and attendance information in a database.
* To provide teachers with an attendance dashboard.
* To allow manual attendance correction.
* To generate attendance reports.
* To export attendance records as CSV.
* To provide a simple and user-friendly web interface.

---

## ✨ Features

### 👤 Student Registration

* Register students using a webcam.
* Enter student name, roll number, and class.
* Capture the student's face.
* Detect the face from the captured image.
* Generate a face encoding.
* Store student details in the database.

### 📷 Face Recognition Attendance

* Access the webcam through the browser.
* Capture classroom images.
* Detect faces automatically.
* Generate face encodings.
* Compare detected faces with registered students.
* Automatically mark recognized students as **Present**.
* Display unrecognized faces as **Unknown**.

### 📊 Attendance Dashboard

* View daily attendance.
* Display Present and Absent students.
* View attendance statistics.
* Monitor attendance records.

### ✏️ Manual Attendance Correction

Teachers can manually update attendance when automatic recognition produces an incorrect result.

### 📄 Attendance Reports

The reports section allows teachers to:

* Select a specific date.
* View attendance records.
* Check Present/Absent status.
* Correct attendance manually.
* Export attendance records as CSV.

### 💾 Database Management

The system uses SQLite to store:

* Student information.
* Face encodings.
* Attendance records.
* Attendance date and time.
* Attendance status.
* Recognition information.

---

# 🛠️ Technologies Used

| Technology           | Purpose                                  |
| -------------------- | ---------------------------------------- |
| **Python**           | Backend programming                      |
| **Flask**            | Web application framework                |
| **OpenCV**           | Image processing                         |
| **face_recognition** | Face detection and recognition           |
| **dlib**             | Face recognition processing              |
| **NumPy**            | Numerical operations                     |
| **Pillow**           | Image processing                         |
| **SQLite**           | Database                                 |
| **Flask-SQLAlchemy** | Database management                      |
| **HTML5**            | Web page structure                       |
| **CSS3**             | Web page styling                         |
| **JavaScript**       | Frontend functionality                   |
| **Git**              | Version control                          |
| **GitHub**           | Source-code management and collaboration |

---

# 📂 Project Structure

```text
ai-classroom-attendance-system/
│
├── app.py
├── models.py
├── face_utils.py
├── requirements.txt
├── README.md
├── LICENSE
├── .gitignore
│
├── database/
│   └── .gitkeep
│
├── known_faces/
│   └── .gitkeep
│
├── templates/
│   ├── base.html
│   ├── index.html
│   ├── register.html
│   ├── attendance.html
│   └── reports.html
│
└── static/
    ├── css/
    │   └── style.css
    │
    └── js/
        ├── webcam.js
        ├── register.js
        ├── attendance.js
        └── reports.js
```

---

# 🔄 System Workflow

```text
                    START
                      │
                      ▼
             Student Registration
                      │
                      ▼
              Capture Face Image
                      │
                      ▼
             Detect Student Face
                      │
                      ▼
            Generate Face Encoding
                      │
                      ▼
             Store Student Details
                      │
                      ▼
              Take Attendance
                      │
                      ▼
             Capture Webcam Image
                      │
                      ▼
                Detect Faces
                      │
                      ▼
          Generate Face Encodings
                      │
                      ▼
        Compare With Registered Faces
                      │
              ┌───────┴───────┐
              │               │
              ▼               ▼
         Recognized        Unknown
              │
              ▼
       Mark Attendance
              │
              ▼
         Finalize Day
              │
              ▼
        Generate Reports
              │
              ▼
              END
```

---

# 👤 Student Registration Process

The student registration process works as follows:

1. Open the **Register Student** page.
2. Enter:

   * Student Name
   * Roll Number
   * Class
3. Allow webcam access.
4. Capture the student's face.
5. The system checks the captured image.
6. The system detects the face.
7. A face encoding is generated.
8. Student information is stored in the database.

---

# 📷 Attendance Process

The attendance process works as follows:

1. Open the **Take Attendance** page.
2. Allow browser webcam access.
3. Capture an image using the webcam.
4. The system detects faces.
5. Face encodings are generated.
6. The generated encodings are compared with registered students.
7. Recognized students are marked **Present**.
8. Unknown faces are displayed as **Unknown**.
9. The teacher can finalize the attendance for the day.

---

# ✅ Finalize Day

After completing attendance, the teacher can use **Finalize Day**.

The system checks all registered students.

```text
Student has attendance record
            │
            ▼
          PRESENT

Student does not have attendance record
            │
            ▼
           ABSENT
```

This helps ensure that students who were not recognized or did not receive an attendance record are marked absent.

---

# 📊 Attendance Reports

The Reports page allows teachers to:

* Select an attendance date.
* View student attendance.
* Check Present/Absent status.
* Manually correct attendance.
* Export attendance records.

The attendance data can be exported as a **CSV file** for further analysis using spreadsheet software.

---

# 🔌 Application Routes

## 🌐 Web Pages

| Method | Route         | Description                  |
| ------ | ------------- | ---------------------------- |
| GET    | `/`           | Today's attendance dashboard |
| GET    | `/register`   | Student registration page    |
| GET    | `/attendance` | Attendance page              |
| GET    | `/reports`    | Attendance reports page      |

---

## 🔗 API Endpoints

| Method | Endpoint                  | Description                         |
| ------ | ------------------------- | ----------------------------------- |
| POST   | `/api/register`           | Register a student                  |
| POST   | `/api/mark_attendance`    | Recognize faces and mark attendance |
| POST   | `/api/finalize_day`       | Finalize daily attendance           |
| POST   | `/api/correct_attendance` | Correct attendance manually         |

---

## 📥 Export

| Method | Route                         | Description                      |
| ------ | ----------------------------- | -------------------------------- |
| GET    | `/export.csv?date=YYYY-MM-DD` | Export attendance records as CSV |

---

# 🗃️ Database Design

The project uses **SQLite** for local database storage.

## Student

The Student table stores information such as:

```text
Student ID
Name
Roll Number
Class
Photo Path
Face Encoding
Created Date/Time
```

## AttendanceLog

The AttendanceLog table stores:

```text
Attendance ID
Student ID
Date
Time
Status
Recognition Confidence
Manual Correction Status
```

A unique attendance record is maintained for each student for a particular date.

---

# ⚙️ Installation

## Prerequisites

Install the following before running the project:

* Python 3.9 or later
* Git
* Modern web browser
* Webcam

---

## 1. Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/ai-classroom-attendance-system.git
```

Move into the project directory:

```bash
cd ai-classroom-attendance-system
```

---

## 2. Create a Virtual Environment

### Windows

```bash
python -m venv venv
```

Activate:

```bash
venv\Scripts\activate
```

### Linux / macOS

```bash
python3 -m venv venv
```

Activate:

```bash
source venv/bin/activate
```

---

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 4. Run the Application

```bash
python app.py
```

Open the local Flask address shown in the terminal.

Usually:

```text
http://127.0.0.1:5000
```

Allow webcam access when the browser asks for permission.

---

# 📦 Requirements

The project uses Python packages such as:

```text
Flask
Flask-SQLAlchemy
face_recognition
opencv-python
numpy
Pillow
pandas
```

The exact versions are available in:

```text
requirements.txt
```

Install them using:

```bash
pip install -r requirements.txt
```

---

# 🧪 Testing

The following functions should be tested before the project is considered complete.

## Student Registration

* [ ] Student registration works.
* [ ] Student name is stored correctly.
* [ ] Roll number is stored correctly.
* [ ] Class is stored correctly.
* [ ] Webcam works correctly.
* [ ] Face is detected correctly.
* [ ] Face encoding is generated.

## Attendance

* [ ] Webcam opens correctly.
* [ ] Face detection works.
* [ ] Registered students are recognized.
* [ ] Attendance is marked correctly.
* [ ] Unknown faces are handled correctly.
* [ ] Duplicate attendance is prevented.

## Finalize Day

* [ ] Present students remain Present.
* [ ] Students without attendance are marked Absent.
* [ ] Attendance records are stored correctly.

## Reports

* [ ] Date selection works.
* [ ] Attendance records are displayed.
* [ ] Manual correction works.
* [ ] CSV export works.

---

# 👥 Project Team

## 👩‍💻 Member 1 — LAKSHANYA.N

**Register Number:** `212224230136`

### Responsibilities

* Backend development
* Flask application
* Database management
* Face recognition functionality
* Student registration API
* Attendance API
* Attendance processing

---

## 👩‍💻 Member 2 — ABISHA LINU.L

**Register Number:** `212224040011`

### Responsibilities

* Frontend development
* HTML
* CSS
* JavaScript
* Webcam interface
* Attendance dashboard
* Attendance reports
* User interface improvements

---

# 🔀 GitHub Collaboration

This project is developed by two team members using Git and GitHub.

Each member should work on a separate branch instead of directly modifying the `main` branch.

```text
                         GitHub
                            │
                          main
                         /    \
                        /      \
                       ▼        ▼
                 member-1    member-2
                    │            │
                  Coding       Coding
                    │            │
                 Commit        Commit
                    │            │
                  Push         Push
                    │            │
                    ▼            ▼
              Pull Request  Pull Request
                    │            │
                    └─────┬──────┘
                          ▼
                         main
```

---

# 👩‍💻 Member 1 Git Workflow

Create a branch:

```bash
git checkout -b member-1
```

After completing the work:

```bash
git add .
```

Commit:

```bash
git commit -m "Update backend and face recognition"
```

Push:

```bash
git push -u origin member-1
```

Then create a Pull Request:

```text
member-1 → main
```

---

# 👩‍💻 Member 2 Git Workflow

Create a branch:

```bash
git checkout -b member-2
```

After completing the work:

```bash
git add .
```

Commit:

```bash
git commit -m "Update frontend and attendance reports"
```

Push:

```bash
git push -u origin member-2
```

Then create a Pull Request:

```text
member-2 → main
```

---

# 🔄 Before Starting New Work

Both members should first update their local `main` branch:

```bash
git checkout main
git pull origin main
```

Then switch to their working branch:

```bash
git checkout member-1
```

or:

```bash
git checkout member-2
```

---

# 📋 Recommended Work Division

| Area                 | LAKSHANYA.N | ABISHA LINU.L |
| -------------------- | :---------: | :-----------: |
| Flask Backend        |      ✅      |               |
| Database             |      ✅      |               |
| Face Recognition     |      ✅      |               |
| Student API          |      ✅      |               |
| Attendance API       |      ✅      |               |
| HTML                 |             |       ✅       |
| CSS                  |             |       ✅       |
| JavaScript           |             |       ✅       |
| Webcam UI            |             |       ✅       |
| Dashboard UI         |             |       ✅       |
| Reports UI           |             |       ✅       |
| GitHub Collaboration |      ✅      |       ✅       |

---

# 🔐 Privacy and Security

This project processes **facial biometric information**.

Therefore, real student biometric data should **not** be uploaded to a public GitHub repository.

Do not commit:

```text
Real student photographs
Face encodings
Attendance databases
Passwords
API keys
.env files
Private student information
```

The `.gitignore` file is used to prevent runtime and sensitive files from being tracked.

Before pushing code, always check:

```bash
git status
```

and review your changes before committing.

---

# ⚠️ Limitations

The current version has the following limitations:

* Face recognition accuracy can be affected by lighting conditions.
* Different face angles can reduce recognition accuracy.
* Poor webcam quality can affect detection.
* SQLite is suitable mainly for small-scale/classroom use.
* No liveness detection is currently implemented.
* No authentication system is currently included.
* Recognition thresholds may require tuning.
* Browser camera permissions are required.
* The system is primarily intended for academic/demo purposes.

---

# 🚀 Future Enhancements

The following features can be added in future versions:

* 🔐 Admin login
* 👨‍🏫 Teacher login
* 👨‍🎓 Student login
* 🔑 Role-based access control
* 🛡️ Face liveness detection
* 📊 Advanced attendance analytics
* 📥 Excel export
* 📄 PDF reports
* 📧 Email notifications
* 📱 Mobile-friendly interface
* ☁️ Cloud deployment
* 🗄️ PostgreSQL/MySQL support
* 🏫 Multiple classes and departments
* 📅 Monthly attendance reports
* 📅 Semester attendance reports
* 🔎 Student search
* 📝 Attendance audit history
* 📈 Attendance percentage calculation

---

# 🤝 Contributing

Contributions are welcome.

### Steps

1. Clone the repository.
2. Create a new branch.
3. Make your changes.
4. Test your changes.
5. Commit your changes.
6. Push your branch.
7. Create a Pull Request.
8. Ask the other team member to review it.
9. Merge the Pull Request after approval.

Example:

```bash
git checkout main
git pull origin main

git checkout -b feature-name

git add .

git commit -m "Add new feature"

git push -u origin feature-name
```

---

# 📄 License

This project is licensed under the **MIT License**.

See the `LICENSE` file for more information.

---

# ⭐ Academic Project

This project was developed as an academic project to demonstrate the practical application of:

* Artificial Intelligence
* Face Recognition
* Computer Vision
* Web Application Development
* Database Management
* Python Programming
* Flask
* Git
* GitHub Collaboration

---

# 📌 Project Summary

The **AI-Based Classroom Attendance System** provides an automated approach to classroom attendance using face recognition.

The project combines:

```text
Python
   +
Flask
   +
OpenCV
   +
Face Recognition
   +
SQLite
   +
HTML
   +
CSS
   +
JavaScript
```

to provide a simple and efficient web-based classroom attendance management system.

---

## 👥 Team

**LAKSHANYA.N**
Register Number: `212224230136`

**ABISHA LINU.L**
Register Number: `212224040011`

---

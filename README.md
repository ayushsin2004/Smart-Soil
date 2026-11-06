# 🌱 Smart Soil – AI-Based Soil Health Analysis & Crop Recommendation

<p align="center">
  <strong>An Android-based smart agriculture application for soil analysis, farm management, and crop recommendations.</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Android-green?logo=android" />
  <img src="https://img.shields.io/badge/Language-Java-orange?logo=java" />
  <img src="https://img.shields.io/badge/Image%20Processing-OpenCV-blue" />
  <img src="https://img.shields.io/badge/ML-TensorFlow%20Lite-orange" />
  <img src="https://img.shields.io/badge/Backend-Spring%20Boot-brightgreen?logo=springboot" />
  <img src="https://img.shields.io/badge/Database-MySQL-blue?logo=mysql" />
</p>

---

## 📌 About the Project

**Smart Soil** is an Android-based smart agriculture project designed to help farmers analyze soil characteristics, manage farm information, and receive crop recommendations.

The application combines image processing, machine learning integration, soil parameter analysis, and backend services to provide a digital platform for soil health management.

Users can register, manage their farms, upload soil images through the camera or gallery, access soil analysis features, and maintain records of previous soil tests.

The project explores how mobile application development, computer vision, and machine learning can be applied to agriculture.

## 🎯 Project Objectives

- Simplify soil health assessment through a mobile application.
- Analyze soil images using image processing techniques.
- Explore machine learning-based soil parameter prediction.
- Provide crop recommendations based on soil characteristics.
- Maintain digital records of farms and soil tests.
- Develop an integrated Android and backend architecture.

## ✨ Key Features

### 👤 User Management
- User registration and login.
- Profile management.
- Password recovery and reset screens.
- Local user data persistence.

### 🌾 Farm Management
- Add and manage farm details.
- Edit and delete farm records.
- Organize soil test records by farm.

### 🔬 Soil Analysis
- Upload soil images using the camera or gallery.
- Validate soil image inputs.
- Image preprocessing using OpenCV.
- Soil parameter analysis workflow.
- Integration code for machine learning inference.
- Crop recommendation based on soil parameters.

### 📊 Soil Test History
- Maintain soil test records.
- View previous soil analysis results.
- Access farm-wise test history.
- Store application data locally and through backend services.

### 🤖 Additional Application Features
- AI chat interface.
- Dashboard and custom navigation.
- Soil test details.
- Application settings and user profile screens.

> **Implementation note:** The uploaded source code includes TensorFlow Lite inference integration, but the expected trained model file (`smart_soil_calibrated.tflite`) was not included in the repository archive. A complete working ML prediction pipeline therefore requires the model file and validation. Some additional features may also require backend/API configuration.

---

## 🏗️ System Architecture

The project follows a layered architecture consisting of an Android frontend, image processing and ML integration, API communication, and backend/database services.

```text
             USER
               |
               v
      ANDROID APPLICATION
         Java / XML
               |
       +-------+-------+
       |               |
       v               v
  FARM MANAGEMENT   SOIL ANALYSIS
       |               |
       |          IMAGE INPUT
       |               |
       |               v
       |          OPENCV
       |               |
       |               v
       |       ML INFERENCE LAYER
       |       (TensorFlow Lite)
       |               |
       +-------+-------+
               |
               v
        API COMMUNICATION
            Retrofit
               |
       +-------+-------+
       |               |
       v               v
    SUPABASE       SPRING BOOT
                       |
                       v
                 MYSQL DATABASE
```

Local persistence is also implemented using Room and SQLite.

---

## 🛠️ Technology Stack

### Android Development
- Java
- Android Studio
- XML Layouts
- Android SDK
- Material Design

### Machine Learning & Image Processing
- OpenCV
- TensorFlow Lite / LiteRT integration
- Image preprocessing
- Regression and classification concepts

### Backend Development
- Java
- Spring Boot
- Spring Data JPA
- REST APIs
- Retrofit

### Database & Storage
- MySQL
- SQLite
- Room Database
- Supabase

### Development Tools
- Git
- GitHub
- Gradle
- Android Studio
- IntelliJ IDEA / compatible Java IDE

---

## 📂 Project Structure

```text
Smart-Soil/
│
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/example/smart_soil/
│   │   │   │   ├── activities/
│   │   │   │   ├── adapters/
│   │   │   │   ├── database/
│   │   │   │   ├── repository/
│   │   │   │   ├── services/
│   │   │   │   └── utils/
│   │   │   │
│   │   │   ├── res/
│   │   │   ├── assets/
│   │   │   └── AndroidManifest.xml
│   │   │
│   │   ├── androidTest/
│   │   └── test/
│   │
│   └── build.gradle.kts
│
├── backend/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   └── resources/
│   │   └── test/
│   │
│   └── build.gradle.kts
│
├── gradle/
├── gradlew
├── gradlew.bat
├── build.gradle.kts
├── settings.gradle.kts
├── gradle.properties
├── package.json
├── package-lock.json
├── DATABASE_IMPLEMENTATION.md
├── README.md
└── .gitignore
```

---

## ⚙️ Requirements

Before running the project, make sure you have:

- Android Studio
- Android SDK
- JDK 17
- Gradle wrapper included in the repository
- MySQL Server (for the Spring Boot backend)
- Git
- An Android emulator or physical Android device

The Android application is configured with:
- Minimum SDK: 24
- Target SDK: 34
- Compile SDK: 34
- Java compatibility: 17

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/ayushsin2004/Smart-Soil.git
```

### 2. Open the Project

1. Open Android Studio.
2. Select **Open**.
3. Navigate to the cloned `Smart-Soil` directory.
4. Allow Gradle to sync.
5. Resolve any missing SDK or dependency requirements.

### 3. Configure Backend

The project includes a Spring Boot backend and MySQL integration.

1. Install and start MySQL Server.
2. Create the required database.
3. Configure database connection properties.
4. Set the appropriate environment variables or local configuration.
5. Start the backend from the project root:

```bash
./gradlew :backend:bootRun
```

On Windows:

```bat
gradlew.bat :backend:bootRun
```

The default backend port should be checked in your local configuration.

### 4. Configure API Services

Configure the required Supabase project URL, publishable key, and other API credentials using your own development configuration.

Never commit private API keys, database passwords, service-role keys, or production credentials to GitHub.

### 5. Run the Android Application

1. Connect an Android device or start an emulator.
2. Select the `app` run configuration.
3. Click **Run** in Android Studio.
4. Test the application features.

> The ML prediction functionality requires the expected trained TensorFlow Lite model asset. It is not included in the uploaded source archive.

---

## 🗄️ Database Implementation

The Android application includes local database persistence using Room ORM and SQLite.

The database layer supports:
- User records.
- Farm records.
- Soil test records.
- Data access objects (DAOs).
- Local persistence.
- Repository-based data operations.

The backend also includes Spring Data JPA and MySQL integration.

For additional implementation details, see [`DATABASE_IMPLEMENTATION.md`](DATABASE_IMPLEMENTATION.md).

---

## 🔬 Machine Learning & Image Processing

The project includes a soil image analysis workflow.

The intended processing pipeline is:

1. Capture or upload a soil image.
2. Validate the image.
3. Process the image using OpenCV.
4. Extract visual characteristics.
5. Pass processed input to the ML inference layer.
6. Analyze soil parameter predictions.
7. Generate crop recommendations based on available soil parameters.

The source includes TensorFlow Lite integration code and parameter normalization logic.

**Current limitation:** The trained model file `smart_soil_calibrated.tflite` was not present in the supplied project archive. The trained model, its dataset, and measured evaluation results must be added or documented separately before claiming a fully operational ML prediction system.

---

## 🔐 Security Considerations

- Keep API credentials outside source-controlled files.
- Use environment variables for backend secrets.
- Apply proper authentication and authorization checks.
- Protect user and farm data.
- Configure database permissions securely.
- Avoid exposing production credentials in public repositories.

This project is intended for educational and development purposes.

---

## 🚧 Future Improvements

- [ ] Integrate and validate the trained TensorFlow Lite model.
- [ ] Improve soil nutrient prediction accuracy.
- [ ] Add model evaluation metrics.
- [ ] Improve crop recommendation using validated agricultural datasets.
- [ ] Strengthen backend authentication and authorization.
- [ ] Implement secure API key management.
- [ ] Add PDF export for soil analysis reports.
- [ ] Improve offline functionality and data synchronization.
- [ ] Add weather information integration.
- [ ] Improve dashboard analytics and visualization.
- [ ] Expand automated testing.

---

## 👨‍💻 Developer

### Ayush Jainendra Singh

**MCA Student | Computer Science | Android Development | Cybersecurity & Machine Learning Enthusiast**

- GitHub: [@ayushsin2004](https://github.com/ayushsin2004)
- LinkedIn: [Ayush Singh](https://www.linkedin.com/in/ayushsin2004/)

---

## 📜 License

No open-source license has currently been specified.

A license can be added after deciding how the project may be used, modified, and distributed.

---

<p align="center">
  <strong>Smart Soil – Exploring the role of technology in smarter agriculture 🌱</strong>
</p>

<p align="center">
  Developed by <strong>Ayush Jainendra Singh</strong>
</p>

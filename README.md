# Multimodal Skin Disease Detection and Diagnosis Support System

**An AI-powered research application combining dermatological image analysis and symptom-based prediction using multimodal late fusion.**

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Django](https://img.shields.io/badge/Django-5.1.5-green?logo=django)
![YOLO](https://img.shields.io/badge/YOLO-v12s-purple)
![PostgreSQL](https://img.shields.io/badge/Database-PostgreSQL-blue?logo=postgresql)
![Project](https://img.shields.io/badge/Status-Research%20Prototype-orange)

## Overview

Skin diseases can exhibit visually similar characteristics, making accurate identification challenging through image analysis alone. This project explores a multimodal artificial intelligence approach that combines dermatological image analysis with structured patient-reported symptoms.

The system integrates deep learning and traditional machine learning models through a **late-fusion architecture** to generate predictions using two complementary information sources.

Developed as a Computer Science Final Year Project, this research-based application demonstrates the integration of AI models with a Django web application and database-backed functionality.

The application currently runs locally and is presented as a working research prototype rather than a publicly deployed or clinically validated diagnostic product.

## Key Features

- **Image-Based Prediction:** Analyzes uploaded skin images using the YOLOv12s model.
- **Symptom-Based Prediction:** Processes structured symptom information using Logistic Regression.
- **Multimodal Late Fusion:** Combines predictions from image and symptom modalities.
- **AI Model Integration:** Connects machine learning and deep learning models with backend application functionality.
- **REST API Backend:** Uses Django REST Framework for backend services.
- **User Authentication:** Supports application authentication and configured social login integrations.
- **Database Integration:** Uses PostgreSQL for persistent application data.
- **Interactive Application:** Provides a web-based interface for user interaction and prediction workflows.

## System Architecture

The application follows a multimodal processing pipeline.

```mermaid
flowchart TD
    A[User Input] --> B[Skin Image]
    A --> C[Symptoms]
    B --> D[YOLOv12s Model]
    C --> E[Logistic Regression Model]
    D --> F[Image Prediction]
    E --> G[Symptom Prediction]
    F --> H[Late Fusion]
    G --> H
    H --> I[Final Prediction]
    I --> J[Django Application]
    J --> K[User Interface]
```

### Multimodal Processing

**1. Image Processing**

Dermatological images are processed using YOLOv12s to extract image-based prediction information.

**2. Symptom Processing**

Structured symptom information is processed using a Logistic Regression model to generate symptom-based predictions.

**3. Late Fusion**

The outputs of both models are combined using a weighted late-fusion strategy to produce a multimodal prediction.

## Technology Stack

| Category | Technologies |
|---|---|
| Programming Language | Python |
| Deep Learning | PyTorch, YOLOv12s |
| Machine Learning | Scikit-learn, Logistic Regression |
| Backend Framework | Django 5.1.5 |
| REST API | Django REST Framework |
| Database | PostgreSQL |
| Image Processing | OpenCV, Pillow |
| Data Processing | NumPy, Pandas |
| Authentication | Django Allauth |
| Static File Management | WhiteNoise |
| Environment Configuration | python-dotenv |
| Development Environment | Google Colab, Local Environment |

## Dataset and Research Methodology

The research explored two complementary data modalities:

| Dataset | Description |
|---|---|
| Dermatological Images | 2,880 skin images |
| Structured Symptom Records | 248 records |
| Image Model | YOLOv12s |
| Symptom Model | Logistic Regression |
| Fusion Strategy | Weighted Late Fusion |
| Target Conditions | 16 skin conditions |

The image and symptom modalities were processed separately before their prediction outputs were combined through late fusion.

*Dataset sources, usage rights, and licensing should be checked before redistribution. Dataset files are not necessarily included in this repository.*

## Repository Structure

The repository is organized into Django application modules and supporting project components.

```text
multimodal-skin-disease-detection/
│
├── chatbot/
├── media/
├── predictor/
├── reviews/
├── skin_identifier/
├── skinpredictor/
├── users/
├── utils/
│
├── manage.py
├── requirements.txt
├── runtime.txt
├── render.yaml
├── .gitignore
│
└── README.md
```

Additional files and model assets may be present in the repository.

### Main Components

- `predictor/` — prediction-related application functionality.
- `skin_identifier/` — skin identification functionality.
- `chatbot/` — chatbot-related functionality.
- `users/` — user management and authentication.
- `reviews/` — review-related functionality.
- `skinpredictor/` — main Django project configuration, URLs, and application settings.
- `utils/` — shared utilities and supporting functionality.
- `manage.py` — Django management entry point.

## Installation and Local Setup

Follow these instructions to run the application in a local development environment.

### Prerequisites

- Python 3.x
- PostgreSQL
- Git
- pip

### 1. Clone the Repository

```bash
git clone https://github.com/aleena-azam510/multimodal-skin-disease-detection.git
cd multimodal-skin-disease-detection
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

Activate the environment.

**Windows**

```bash
venv\Scripts\activate
```

**Linux/macOS**

```bash
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure Environment Variables

The project uses `python-dotenv` to load environment variables from a `.env` file located in the project root.

Create a `.env` file alongside `manage.py`.

Example:

```env
SECRET_KEY=your-django-secret-key
DEBUG=True

ALLOWED_HOSTS=localhost,127.0.0.1
CSRF_TRUSTED_ORIGINS=http://localhost:8000

DATABASE_URL=postgresql://username:password@localhost:5432/database_name

# Google Authentication
GOOGLE_CLIENT_ID=
GOOGLE_SECRET=

# Facebook Authentication
FACEBOOK_CLIENT_ID=
FACEBOOK_SECRET=

# GitHub Authentication
GITHUB_CLIENT_ID=
GITHUB_SECRET=

# Email Configuration
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_HOST_USER=
EMAIL_HOST_PASSWORD=
```

Replace the example values with your actual local configuration.

**Important:** Never commit your `.env` file, Django secret key, database credentials, OAuth secrets, or email passwords to GitHub.

### 5. Configure PostgreSQL

1. Ensure PostgreSQL is installed and running.
2. Create a local database.
3. Update the `DATABASE_URL` value in `.env`.
4. Verify that the database credentials and connection settings are correct.

### 6. Apply Database Migrations

```bash
python manage.py migrate
```

### 7. Start the Development Server

```bash
python manage.py runserver
```

Open the application in your browser:

**http://127.0.0.1:8000/**

*Note: The application may also require model weights and other assets to be available at their configured paths. Ensure these files are present before running prediction functionality.*

## Research Publication

This project resulted in the following research publication:

**Title:** Skin Diseases Detection and Diagnosis Support System Using YOLOv12s and Late Fusion Technique

**Authors:** Sahil Muneer, Aleena Azam, Yasir Arfat Malkani, Noor e Hira

**Journal:** International Journal of Innovations in Science & Technology (IJIST)

**Volume:** 7, Issue 10, Pages 55–67

**Publication Date:** November 2025

- [Read the Published Research Paper](https://journal.50sea.com/index.php/IJIST/article/view/1723)
- [View DOI](https://doi.org/10.33411/IJIST/1723)

## Project Status

**Completed Academic Research Project — Working Local Prototype**

The application supports image-based and symptom-based prediction workflows and integrates the corresponding machine learning components with a Django backend.

The project is currently maintained as a locally executable research prototype. It is not presented as a publicly hosted application or a clinically validated diagnostic system.

## Limitations and Future Enhancements

Potential future improvements include:

- Evaluation using larger and more diverse dermatological datasets.
- Further validation of multimodal fusion performance.
- Improving model generalization and prediction robustness.
- Expanding testing across different image acquisition conditions.
- Optimizing model inference and backend performance.
- Preparing a publicly accessible demonstration deployment.

## Author

**Aleena Azam**

BS Computer Science — Gold Medalist

GitHub: [aleena-azam510](https://github.com/aleena-azam510)

---

*This project was developed for academic and research purposes. Its predictions are experimental and should not be used as a substitute for professional medical diagnosis.*

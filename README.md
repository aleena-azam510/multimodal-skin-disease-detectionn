# Multimodal Skin Disease Detection and Diagnosis Support System

A research-based AI application that combines dermatological image analysis with patient-reported symptoms to support skin disease identification through a multimodal late-fusion approach.

## Project Overview

Skin conditions can present with visually similar characteristics, making image-only classification challenging. This project explores a multimodal approach that combines visual features extracted from skin images with structured symptom information.

The system integrates deep learning and machine learning techniques to generate predictions from two input modalities:

- **Image-based analysis:** Uses YOLOv12s for dermatological image analysis.
- **Symptom-based analysis:** Uses a Logistic Regression model to process structured symptom information.
- **Multimodal fusion:** Combines the outputs of both models using a late-fusion strategy.

The project was developed as a Final Year Project and research prototype. The application runs locally and is not presented as a clinically validated diagnostic system.

## Key Features

- Skin disease prediction from uploaded images.
- Symptom-based prediction using structured patient inputs.
- Multimodal prediction through late fusion.
- Backend API functionality using Django REST Framework.
- Database integration for application data.
- User-facing application interface.
- Research-oriented model evaluation.

## System Architecture

The application follows a multimodal processing pipeline:

1. Image input is processed by the YOLOv12s model.
2. Symptom information is processed by the Logistic Regression model.
3. Outputs from both modalities are combined through late fusion.
4. The resulting prediction is returned through the application backend.

## Technology Stack

| Area | Technologies |
|---|---|
| Programming language | Python |
| Deep learning | PyTorch, YOLOv12s |
| Machine learning | Scikit-learn, Logistic Regression |
| Backend | Django, Django REST Framework |
| Database | PostgreSQL |
| Image processing | OpenCV, Pillow |
| Data processing | NumPy, Pandas |
| Development | Google Colab, Local Environment |

## Dataset and Methodology

The research used dermatological image data and structured symptom records.

- Image dataset: 2,880 dermatological images.
- Symptom dataset: 248 structured records.
- Image model: YOLOv12s.
- Symptom model: Logistic Regression.
- Fusion strategy: Weighted late fusion.

Dataset usage and licensing should be checked against the original sources before redistribution.

## Repository Structure

The project is organized into Django application modules, model-related components, utilities, and supporting configuration files.

Main components include:

- `predictor/` — prediction-related functionality.
- `chatbot/` — chatbot-related functionality.
- `skin_identifier/` — skin identification functionality.
- `skinpredictor/` — project configuration or prediction-related components.
- `users/` — user-related functionality.
- `reviews/` — review-related functionality.
- `utils/` — supporting utilities.
- `manage.py` — Django management entry point.

## Local Installation and Execution

### 1. Clone the repository

```bash
git clone https://github.com/aleena-azam510/multimodal-skin-disease-detection.git
cd multimodal-skin-disease-detection
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

Activate it:

**Windows**
```bash
venv\Scripts\activate
```

**Linux/macOS**
```bash
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure environment variables

Create a local `.env` file using the environment variables required by the project settings.

Do not commit credentials, secret keys, database passwords, or other sensitive configuration.

### 5. Configure the database

Configure PostgreSQL using your local database credentials and the settings expected by the application.

### 6. Apply database migrations

```bash
python manage.py migrate
```

### 7. Start the development server

```bash
python manage.py runserver
```

Open the local application at:

`http://127.0.0.1:8000/`

**Note:** These are the standard Django setup steps. Confirm the project's actual environment variables, database configuration, model-weight locations, and any additional setup steps before treating this section as a verified installation guide.

## Research Publication

**Title:** Skin Diseases Detection and Diagnosis Support System Using YOLOv12s and Late Fusion Technique

**Journal:** International Journal of Innovations in Science & Technology (IJIST)

**Volume:** 7, Issue 10, Pages 55–67, November 2025

**Authors:** Sahil Muneer, Aleena Azam, Yasir Arfat Malkani, Noor e Hira

**Publication:** https://journal.50sea.com/index.php/IJIST/article/view/1723

**DOI:** https://doi.org/10.33411/IJIST/1723

## Project Status

**Status:** Completed academic research project / working local prototype.

The application supports image-based and symptom-based prediction locally. It is not currently presented as a publicly hosted service or a clinically validated medical diagnostic tool.

## Limitations and Future Work

- Further evaluation using larger and more diverse datasets.
- Improved model generalization and robustness.
- Additional testing across different image conditions.
- Further validation of multimodal fusion performance.
- Potential deployment as a hosted demonstration application.

## Author

**Aleena Azam**

BS Computer Science — Gold Medalist

GitHub: https://github.com/aleena-azam510

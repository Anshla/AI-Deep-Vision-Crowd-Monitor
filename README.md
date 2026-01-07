# Deep Vision Crowd Monitor

Deep Vision Crowd Monitor is an AI-based crowd density estimation system designed for **image-level crowd analysis**.  
The project uses deep learning models such as **CSRNet** and **YOLOv8** to estimate crowd count, visualize density distribution, and trigger **email alerts** when predefined thresholds are exceeded.

The current implementation focuses on **single image uploads** and dense crowd scenarios. Support for video processing and live webcam monitoring is planned as future enhancements.

---

## Features

### Crowd Density Estimation
- Image-based crowd analysis using CSRNet
- Density map generation for dense crowd scenes
- Accurate crowd count estimation

### Hybrid Model Support
- CSRNet for density-based estimation
- YOLOv8 for person detection in sparse scenes
- Modular design to support adaptive strategies

### Email Alert System
- Threshold-based crowd alerts
- SMTP-based email notifications
- Configurable recipients and credentials

### Visualization
- Density heatmaps
- Total crowd count display
- Streamlit-based interactive interface

---

## Live Deployment

The application has been **successfully deployed on Streamlit Cloud** and is publicly accessible.

**Live Application:**  
https://anshla-csrnet.streamlit.app/

The deployed version allows you to:
- Upload crowd images
- View crowd density maps
- Check estimated crowd counts

> Note: Due to file size limitations, trained model files are loaded externally.  
> Refer to the **Model Files** section when running the application locally.

---

## Model Files

Due to GitHub file size limitations, trained model weights are **not included** in this repository.

**Download trained models from Google Drive:**  
https://bit.ly/ai-deepvision-models

### Included Models
- **best_csrnet_partB.pth** – CSRNet model for dense crowd estimation
- **yolov8n.pt** – YOLOv8 model for person detection

After downloading, place the files inside the `models/` directory:

```text
models/
├── best_csrnet_partB.pth
└── yolov8n.pt
```
## Installation and Setup

### Step 1: Clone the Repository
```bash
git clone https://github.com/Anshla/AI-Deep-Vision-Crowd-Monitor.git
cd AI-Deep-Vision-Crowd-Monitor
```
### Step 2: Install Dependencies
```bash
pip install -r requirements.txt
```
### Step 3: Download Model Files

Download the trained models from Google Drive:
https://bit.ly/ai-deepvision-models

Place the downloaded files inside the `models/` directory:
```text
models/
├── best_csrnet_partB.pth
└── yolov8n.pt
```
## Email Alert Configuration 

The project supports email alerts using **Gmail SMTP**.

### Step 1: Create Gmail App Password
If your Gmail account has **2-Factor Authentication** enabled:
1. Go to **Google Account → Security**
2. Generate an **App Password**
3. Use this password as `EMAIL_PASSWORD`

---

### Step 2: Configure Environment Variables

Create a `.env` file with the following values:

```text
EMAIL_SENDER=your-email@gmail.com
EMAIL_PASSWORD=your-app-password
EMAIL_RECEIVERS=receiver1@gmail.com,receiver2@gmail.com
SMTP_SERVER=smtp.gmail.com
SMTP_PORT=587
```

## Local Testing

### Install dotenv (if required)
```bash
pip install python-dotenv
```
### Load environment variables in the application
```python
from dotenv import load_dotenv
load_dotenv()
```
### Run the Application
```bash
streamlit run app.py
```
Open in browser:
```text
http://localhost:8501
```
## Logging

- Email delivery failures are logged to the terminal
- Useful for debugging SMTP or credential-related issues
```
```````````
## Project Structure

```text
AI-Deep-Vision-Crowd-Monitor/
├── app.py
├── email_alert.py
├── requirements.txt
├── README.md
├── models/
│   └── (download from Google Drive)
├── utils/
└── sample_images/

```
## Future Scope

The following features are planned for future development:
- Video-based crowd analysis
- Live webcam crowd monitoring
- Real-time analytics dashboard
```
```
## Technologies Used

- Streamlit
- PyTorch
- OpenCV
- CSRNet
- YOLOv8 (Ultralytics)
- NumPy
- Matplotlib
- SMTP (Email alerts)

---

## Contributor

**Anshla Pagdal**  
Project development, model integration, deployment, and alert system

---

## License

This project is licensed under the **Apache License 2.0**.  
See the `LICENSE` file for more details.

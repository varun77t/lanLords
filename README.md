# LAN LORDS - Automated Complaint Processing System

## Overview
The **LAN LORDS** project is a customer complaint processing system designed to automate the classification and resolution of customer complaints using advanced AI/ML models and a robust backend infrastructure. The system handles various forms of input (image, audio, video) and processes them to extract relevant information, which is then used for automated complaint classification and resolution. The project includes features like real-time complaint tracking, predictive analysis, and multilingual chatbot support.

## Key Features

### Preprocessing Models:
- **Image Preprocessing**: Using OpenCV for image input.
- **Video Preprocessing**: Frame extraction using FFmpeg and OpenCV for video input.
- **Audio Preprocessing**: Audio sampling using Librosa for audio input.

### Model Ensemble:
- **OCR Model**: Text extraction from images using Tesseract OCR.
- **Image/Audio/Video → Text Model**: Using CLIP and Random Forests to convert multimedia inputs into text.
- **Predictive Analysis**: Utilizing the XGBoost model to predict future issues based on past complaints.

### Automated Complaint Processing:
- Classification and assignment of complaints based on extracted data.

### Customer Interface:
- **Real-time complaint tracking**.
- **Complaint registration**.
- **Multilingual chatbot (AdamW)** for assistance.
- **Feedback mechanism** for service improvement.

### Admin Interface:
- Manage **complaint logs** and resolutions.
- Handle **manual assignment** for wrongly classified complaints.
- **Multilingual chatbot** for admin assistance.
- Predict **future issues** based on data trends.

### Backend Web Server:
- **Node.js-based server** handling API requests and managing interactions between the frontend and models.

### Database:
- **MongoDB**: Used to store complaint data, logs, and system metadata.
- **AWS S3 Object Store**: Used for storage of image, audio, and video inputs.

## Technology Stack
- **Frontend**: Customer and admin interfaces for complaint registration, tracking, and resolution.
- **Backend**: Node.js with a robust API handling data flow between interfaces and models.
- **Database**: MongoDB for data persistence, AWS S3 for media storage.

### AI/ML Models:
- **Preprocessing**: OpenCV, FFmpeg, Librosa.
- **Text Models**: CLIP, Random Forests.
- **OCR**: Tesseract OCR.
- **Predictive Model**: XGBoost.

## Project Structure

```
lannn/
├── final-1711/
│   ├── backend/              # Node.js Express server
│   │   ├── index.js
│   │   ├── package.json
│   │   ├── controllers/      # Request handlers
│   │   ├── models/           # Database schemas
│   │   ├── routes/           # API endpoints
│   │   └── s3Upload.js       # AWS S3 integration
│   │
│   ├── frontend/             # React-based UI
│   │   ├── src/
│   │   │   ├── Components/   # React components
│   │   │   ├── App.js
│   │   │   └── i18n.js       # Multilingual support
│   │   └── package.json
│   │
│   └── mlApi/                # ML model endpoints
│       ├── audio.py
│       ├── video.py
│       └── codebase.py
│
└── README.md
```

## Getting Started

### Prerequisites
- Node.js v14+
- Python 3.8+
- MongoDB
- AWS S3 Account (for media storage)
- Git

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/varun77t/lanLords.git
   cd lanLords/final-1711
   ```

2. **Setup Backend**
   ```bash
   cd backend
   npm install
   cp .env.example .env  # Configure your environment variables
   npm start
   ```

3. **Setup Frontend**
   ```bash
   cd ../frontend
   npm install
   npm start
   ```

4. **Setup ML API**
   ```bash
   cd ../mlApi
   pip install -r requirements.txt
   python test_main.py
   ```

## Environment Variables

Create a `.env` file in the backend directory with:
```
MONGODB_URI=your_mongodb_connection_string
AWS_ACCESS_KEY_ID=your_aws_access_key
AWS_SECRET_ACCESS_KEY=your_aws_secret_key
AWS_REGION=your_aws_region
PORT=5000
```

## Features in Action

- **Upload Complaints**: Submit complaints via image, audio, or video
- **AI Processing**: Automatic classification using ML models
- **Real-time Tracking**: Monitor complaint status in real-time
- **Multilingual Support**: Available in English, Hindi, and Kannada
- **Predictive Analytics**: Identify recurring issues
- **Admin Dashboard**: Comprehensive complaint management

## Contributing

Feel free to fork this repository and submit pull requests with improvements.

## License

This project is licensed under the MIT License - see LICENSE file for details.

# Image Processing Web Service

A full-stack web application providing image enhancement routines, dominant color extraction, and user profile media management built with Flask, Pillow, and MongoDB.

---

## Technical Stack

- **Backend Framework**: Python / Flask
- **Image Processing Engine**: Pillow (PIL)
- **Database & ODM**: MongoDB with MongoEngine
- **User Authentication**: Flask-Login session management with salted password hashing

---

## Core Capabilities

- **Image Enhancement Pipeline**:
  - Color saturation adjustments (`ImageEnhance.Color`)
  - Dynamic brightness scaling (`ImageEnhance.Brightness`)
  - Contrast enhancement (`ImageEnhance.Contrast`)
  - Kernel-based sharpness filters (`ImageEnhance.Sharpness`)
- **Color Analysis**: Top-K dominant color clustering via pixel histogram frequency analysis.
- **Media Persistence**: Per-user image storage, revision history (`.copy` fallback), and download routines.
- **Session Management**: User registration, login authentication, and secure profile galleries.

---

## Directory Layout

```
Flask_Image-Processing/
├── backend/
│   ├── image_routines.py     # Pillow manipulation and color analysis functions
│   ├── routes.py             # HTTP endpoint controllers
│   ├── models.py             # MongoEngine schemas (User, Image records)
│   ├── forms.py              # WTForms validation schemas
│   └── templates/            # Jinja2 rendering templates
├── static/                   # CSS and client-side assets
├── app.py                    # Application entry point
├── requirements.txt          # Python dependencies
└── Procfile                  # Production deployment configuration
```

---

## Installation & Setup

### 1. Clone the repository
```bash
git clone https://github.com/AmjedKhaled165/Flask_Image-Processing.git
cd Flask_Image-Processing
```

### 2. Configure Environment
```bash
python -m venv venv
# On Windows:
.\venv\Scripts\activate
# On Unix:
source venv/bin/activate

pip install -r requirements.txt
```

### 3. Database Connection
Ensure a local or remote MongoDB instance is running, and export connection variables if required:
```bash
# Optional: Set MongoDB URI if connecting to MongoDB Atlas
set MONGODB_SETTINGS_HOST="mongodb://localhost:27017/image_processing_db"
```

### 4. Run Application
```bash
python app.py
```
The server will start at `http://127.0.0.1:5000`.

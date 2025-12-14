# Setup & Environment Guide

## Supported Python Version

BHV requires **Python 3.8+** for optimal compatibility with healthcare network environments.

## Environment Setup

### Using venv (Recommended)

```bash
# Create virtual environment
python -m venv bhv-env

# Activate (Windows)
bhv-env\Scripts\activate

# Activate (Linux/macOS)
source bhv-env/bin/activate

# Install dependencies (when available)
pip install -r requirements.txt
```

### Using conda

```bash
# Create environment
conda create -n bhv python=3.8

# Activate
conda activate bhv

# Install dependencies (when available)
pip install -r requirements.txt
```

## Required System Dependencies

- **Python 3.8+**
- **SQLite3** (included with Python)
- **Pillow dependencies** (for image processing):
  - Windows: Usually included with Pillow
  - Ubuntu/Debian: `sudo apt-get install libjpeg-dev zlib1g-dev`
  - CentOS/RHEL: `sudo yum install libjpeg-devel zlib-devel`
  - macOS: `brew install libjpeg`

## Environment Configuration

Create a `.env` file in the project root:

```env
# Security
SECRET_KEY=your-secret-key-here-change-in-production

# Database
DB_PATH=./data/bhv.db

# Media Storage
MEDIA_ROOT=./media/uploads

# Application
DEBUG=True
ALLOWED_HOSTS=localhost,127.0.0.1

# Server
HOST=127.0.0.1
PORT=8000
```

## Directory Structure

The application will create these directories automatically:

```
BHV/
├── data/          # Database files
├── media/         # Uploaded images and files
│   └── uploads/   # User-uploaded content
├── logs/          # Application logs
└── .env           # Environment configuration
```

## Quick Start

1. Clone the repository
2. Set up virtual environment
3. Copy `.env.example` to `.env` and configure
4. Run: `python app.py` (single command startup)

## Security Notes

- Change `SECRET_KEY` in production
- Set `DEBUG=False` in production
- Configure proper `ALLOWED_HOSTS` for your network
- Ensure proper file permissions on media directories
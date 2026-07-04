# Development Environment Setup

Before running the RK Health AI Smart Patient Appointment & Medication Reminder System, install the required software and configure the development environment.

---

# Prerequisites

Ensure the following software is installed:

- Python 3.8 or later
- pip (Python Package Manager)
- Git
- Visual Studio Code (Recommended)

Verify the installation:

```bash
python --version
pip --version
```

---

# Create a Virtual Environment

Create a virtual environment to isolate project dependencies.

**Windows**

```bash
python -m venv rkhealth-env
```

Activate the environment:

```bash
rkhealth-env\Scripts\activate
```

**macOS/Linux**

```bash
python3 -m venv rkhealth-env
source rkhealth-env/bin/activate
```

After activation, the terminal should display:

```bash
(rkhealth-env)
```

---

# Install Required Packages

Install Flask:

```bash
pip install Flask==3.0.3
```

Install Groq SDK:

```bash
pip install groq==0.11.0
```

Install python-dotenv:

```bash
pip install python-dotenv==1.0.1
```

Or install all dependencies using:

```bash
pip install -r requirements.txt
```

---

# Configure Environment Variables

Create a file named:

```
.env
```

Add the following configuration:

```env
GROQ_API_KEY=your_groq_api_key_here
TWILIO_ACCOUNT_SID=your_account_sid
TWILIO_AUTH_TOKEN=your_auth_token
TWILIO_PHONE_NUMBER=your_twilio_phone_number
GOOGLE_SHEET_ID=your_google_sheet_id
GOOGLE_SCRIPT_URL=your_google_apps_script_url
```

---

# Project Directory Structure

```
RK-Health-AI/
│
├── app.py
├── run_public.py
├── requirements.txt
├── README.md
├── .env
├── .gitignore
│
├── static/
│   ├── css/
│   │   └── style.css
│   ├── js/
│   │   └── script.js
│   └── images/
│
├── templates/
│   ├── index.html
│   ├── dashboard.html
│   └── report.html
│
├── utils/
│   ├── ai.py
│   ├── sms.py
│   └── helpers.py
│
└── docs/
```

---

# requirements.txt

Example:

```text
Flask==3.0.3
groq==0.11.0
python-dotenv==1.0.1
requests
```

Generate automatically:

```bash
pip freeze > requirements.txt
```

---

# Run the Application

Activate the virtual environment:

```bash
rkhealth-env\Scripts\activate
```

Run the application:

```bash
python app.py
```

Or

```bash
python run_public.py
```

The application will start at:

```
http://127.0.0.1:5000
```

---

# Verify Installation

Check that:

- Python is installed.
- Virtual environment is active.
- Flask starts without errors.
- Groq API key loads successfully.
- Application opens in the browser.
- Static files (CSS/JS) load correctly.

---

# Security Best Practices

- Never upload the `.env` file to GitHub.
- Add `.env` to `.gitignore`.
- Keep API keys private.
- Use virtual environments for dependency isolation.
- Install only the required packages.

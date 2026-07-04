# System Architecture

## Architecture Overview

The RK Health AI Smart Patient Appointment and Medication Reminder System follows a multi-tier architecture consisting of a frontend interface, backend services, cloud database, AI integration, and third-party communication services.

### Architecture Components

- Frontend (HTML, CSS, JavaScript)
- Google Apps Script Backend
- Google Sheets Database
- Groq AI Summary Service
- Twilio SMS API
- Google Calendar API

---

# Architectural Diagram

```
                        +---------------------------+
                        |        User               |
                        +-------------+-------------+
                                      |
                                      |
                         HTML / CSS / JavaScript
                                      |
                                      v
                     +-------------------------------+
                     |     Frontend Dashboard         |
                     +-------------------------------+
                                      |
                             HTTP Requests
                                      |
                                      v
                     +-------------------------------+
                     | Google Apps Script Backend     |
                     +-------------------------------+
                 _________|_____________|_____________
                |         |             |             |
                |         |             |             |
                v         v             v             v
      Google Sheets   Groq AI API   Twilio SMS   Google Calendar
        Database       (Llama 3.3)      API           API
                |             |             |             |
                +-------------+-------------+-------------+
                              |
                              v
                     Dashboard Response
```

---

# Frontend Functionality

The frontend provides a responsive dashboard that enables healthcare providers and patients to manage healthcare information efficiently.

## User Features

- Add appointments
- Update appointments
- Delete appointments
- Manage medication schedules
- Store doctor notes
- Maintain patient records
- View healthcare logs
- Generate AI healthcare summaries
- View reports and statistics
- Receive medication reminders
- Access appointment schedules
- Mobile-friendly dashboard
- Desktop-friendly interface

---

# Frontend Workflow

1. User logs into the dashboard.
2. User enters appointment details.
3. User adds medication schedules.
4. User records doctor notes.
5. User saves patient information.
6. User requests an AI-generated summary.
7. Dashboard displays reports and reminders.
8. SMS notifications are sent automatically.
9. Calendar events are created.

---

# Backend Responsibilities

The backend is implemented using Google Apps Script.

Its responsibilities include:

- Receive frontend requests
- Validate user input
- Sanitize input data
- Store healthcare records
- Retrieve patient information
- Update records
- Delete records
- Generate dashboard statistics
- Generate AI summaries
- Schedule appointments
- Send SMS reminders
- Communicate with Google Sheets
- Connect with Google Calendar
- Call Groq AI API

---

# Backend Functions

| Function | Purpose |
|----------|---------|
| doGet(e) | Loads the web application |
| addLog() | Adds appointment and patient records |
| getLogs() | Retrieves healthcare records |
| updateLog() | Updates patient information |
| deleteLog() | Removes healthcare records |
| getStats() | Returns dashboard statistics |
| generateSummary() | Generates AI healthcare summaries |
| sendSMS() | Sends SMS reminders using Twilio |
| runOnce() | Performs initialization tasks |

---

# Google Sheets Database

The application stores healthcare data inside Google Sheets.

Tables include:

- Appointments
- MedicationSchedules
- PatientRecords
- HealthLogs
- Summaries
- Reports

---

# AI Integration

The AI module generates patient-friendly healthcare summaries.

## Workflow

1. Backend receives appointment details.
2. Doctor notes are collected.
3. Medication information is combined.
4. Patient history is prepared.
5. Data is formatted into a prompt.
6. Prompt is sent to Groq API.
7. Llama-3.3-70B-Versatile generates a summary.
8. Backend validates the response.
9. Summary is stored in Google Sheets.
10. Dashboard displays the generated summary.

---

# AI Processing Flow

```
Patient Records
      │
      ▼
Appointment Details
      │
      ▼
Doctor Notes
      │
      ▼
Medication Details
      │
      ▼
Google Apps Script
      │
      ▼
Groq API
      │
      ▼
Llama-3.3-70B-Versatile
      │
      ▼
Generated Healthcare Summary
      │
      ▼
Google Sheets
      │
      ▼
Frontend Dashboard
```

---

# Third-Party Integrations

## Google Sheets

- Stores healthcare records
- Stores AI summaries
- Stores reports

## Twilio

- Appointment reminders
- Medication reminders
- Emergency notifications

## Google Calendar

- Schedule appointments
- Reminder notifications
- Calendar synchronization

## Groq AI

- Generate healthcare summaries
- Analyze doctor notes
- Simplify medical information

---

# Security Features

- Input validation
- Data sanitization
- API key protection
- Environment variable configuration
- Secure cloud storage
- Access control
- HTTPS communication

---

# Advantages

- Cloud-based architecture
- AI-powered healthcare summaries
- Automated SMS reminders
- Calendar integration
- Centralized patient records
- Responsive user interface
- Scalable backend
- Secure data management

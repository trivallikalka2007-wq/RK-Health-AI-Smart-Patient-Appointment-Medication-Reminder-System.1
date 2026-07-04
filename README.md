# Backend Implementation and Cloud Integration

This milestone implements the core backend functionality of the RK Health AI Smart Patient Appointment & Medication Reminder System. The backend is developed using Google Apps Script and integrates with Google Sheets, Groq AI, Twilio SMS, and Google Calendar to provide a complete healthcare management workflow.

---

# Backend Functions

The application backend exposes the following functions:

| Function | Description |
|----------|-------------|
| `doGet(e)` | Loads the web application and serves the dashboard. |
| `addLog()` | Stores new patient appointments and medication records in Google Sheets. |
| `getLogs()` | Retrieves all healthcare records for dashboard display. |
| `updateLog()` | Updates existing patient records and appointment details. |
| `deleteLog()` | Deletes selected healthcare records from the database. |
| `getStats()` | Calculates dashboard statistics such as appointments, reminders, and reports. |
| `generateSummary()` | Generates AI-powered patient health summaries using the Groq API. |
| `sendSMS()` | Sends appointment and medication reminders through Twilio. |
| `runOnce()` | Performs initial setup, creates required sheets, and initializes configuration. |

---

# User Input Processing

The frontend provides forms for entering healthcare information.

### Patient Information

- Patient Name
- Doctor Name
- Appointment Title
- Appointment Date
- Appointment Time
- Medication Name
- Dosage
- Medicine Timing
- Phone Number
- Visit Notes

### Processing Workflow

1. User submits the form.
2. Frontend sends data to Google Apps Script.
3. Backend extracts request parameters.
4. Input validation is performed.
5. Valid records are stored in Google Sheets.
6. Dashboard is updated with the latest information.

---

# Input Validation

The application validates all incoming data before processing.

### Validation Rules

- Patient Name cannot be empty.
- Doctor Name cannot be empty.
- Appointment Date must be valid.
- Appointment Time must be valid.
- Phone Number must follow the correct format.
- Medication Name cannot be empty.
- Dosage information is required.
- Visit Notes should not exceed the allowed length.

---

# Google Sheets Integration

Google Sheets serves as the cloud database for the application.

### Stored Information

- Patient Records
- Appointment Details
- Medication Schedules
- Reminder History
- AI Health Summaries
- Healthcare Reports

### Database Operations

- Create records
- Read records
- Update records
- Delete records
- Generate reports
- Retrieve dashboard statistics

---

# AI Integration

The application integrates with the Groq API using the **llama-3.3-70b-versatile** model.

### AI Workflow

1. Retrieve patient information.
2. Collect appointment details.
3. Collect doctor notes.
4. Gather medication information.
5. Create a structured prompt.
6. Send the request to the Groq API.
7. Generate a patient-friendly summary.
8. Validate the generated response.
9. Store the summary in Google Sheets.
10. Display the summary on the dashboard.

### AI Output Includes

- Visit Overview
- Diagnosis Summary
- Medication Guidance
- Follow-up Instructions
- Lifestyle Recommendations
- Next Appointment Reminder

---

# Twilio SMS Integration

Twilio is used for sending appointment and medication reminders.

### Features

- Format phone numbers
- Send appointment reminders
- Send medication reminders
- Track SMS delivery status
- Update reminder completion history

### SMS Workflow

1. Retrieve reminder information.
2. Format recipient phone number.
3. Generate reminder message.
4. Send SMS through Twilio.
5. Receive delivery status.
6. Update reminder history.

---

# Google Calendar Integration

Google Calendar integration allows users to schedule appointments directly.

### Features

- Generate appointment events
- Add appointment reminders
- Create Google Calendar event links
- Synchronize appointment schedules

### Workflow

1. Retrieve appointment information.
2. Generate Google Calendar event.
3. Create reminder.
4. Display calendar link.
5. User adds the event to their calendar.

---

# Complete Healthcare Workflow

```text
Patient
    │
    ▼
Frontend Dashboard
(HTML • CSS • JavaScript)
    │
    ▼
Google Apps Script Backend
    │
    ├── addLog()
    ├── getLogs()
    ├── updateLog()
    ├── deleteLog()
    ├── getStats()
    ├── generateSummary()
    ├── sendSMS()
    └── runOnce()
    │
    ▼
Google Sheets Database
    │
    ├── Patient Records
    ├── Appointments
    ├── Medications
    ├── Reports
    └── AI Summaries
    │
    ├──────────────┐
    │              │
    ▼              ▼
Groq API      Twilio SMS
    │              │
    ▼              ▼
AI Summary   Reminder Messages
    │
    ▼
Google Calendar
    │
    ▼
Patient Dashboard
```

---

# Key Features

- Patient record management
- Appointment scheduling
- Medication reminder management
- AI-powered health summaries
- Healthcare report generation
- Google Sheets cloud database
- Twilio SMS notifications
- Google Calendar integration
- Dashboard analytics
- Secure API key management

---

# Security Measures

- Input validation
- Data sanitization
- Secure environment variables (`.env`)
- Protected API credentials
- HTTPS communication
- Google authentication
- Restricted access to cloud resources
- `.env` excluded from GitHub using `.gitignore`

---

# Expected Outcome

After completing this milestone, the RK Health AI Smart Patient Appointment & Medication Reminder System will provide:

- Complete patient record management
- Automated appointment scheduling
- Medication reminder notifications
- AI-generated healthcare summaries
- Healthcare report generation
- Google Sheets cloud storage
- Twilio SMS integration
- Google Calendar event creation
- Secure and scalable healthcare workflow

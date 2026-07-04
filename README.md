# Backend Processing and Workflow Management

This milestone implements the complete backend processing workflow for the RK Health AI Smart Patient Appointment & Medication Reminder System using Google Apps Script. It manages healthcare records, cloud storage, AI summary generation, SMS reminders, Google Calendar integration, and dashboard updates.

---

# Core Backend Functions

The backend is organized into reusable functions, each responsible for a specific healthcare operation.

| Function | Purpose |
|----------|---------|
| `doGet(e)` | Receives frontend requests and routes actions to the appropriate backend function. |
| `addLog()` | Stores new patient appointments and medication records in Google Sheets. |
| `getLogs()` | Retrieves healthcare logs for display on the dashboard. |
| `updateLog()` | Updates existing patient, appointment, or medication records. |
| `deleteLog()` | Removes selected healthcare records from storage. |
| `getStats()` | Calculates dashboard statistics such as appointments, reminders, and reports. |
| `generateSummary()` | Generates AI-powered patient health summaries using Groq LLM. |
| `sendSMS()` | Sends medication and appointment reminders using Twilio SMS. |
| `runOnce()` | Executes scheduled backend tasks such as reminders and initialization. |

---

# Backend Request Handling

The backend processes requests submitted from the frontend dashboard.

## Request Handling Workflow

1. Receive request from frontend.
2. Read submitted form data.
3. Validate all inputs.
4. Execute the requested backend function.
5. Store or retrieve data from Google Sheets.
6. Generate AI summary (if requested).
7. Send SMS reminders (if required).
8. Return a structured JSON response.

---

# Input Validation

All user inputs are validated before processing.

### Validation Rules

- Patient Name cannot be empty.
- Doctor Name cannot be empty.
- Appointment Date must be valid.
- Appointment Time must be valid.
- Medication Name is required.
- Dosage must be specified.
- Phone Number must follow the correct format.
- Visit Notes cannot be empty.

---

# Backend Request Flow

```text
Frontend Dashboard
        │
        ▼
Google Apps Script
        │
        ▼
Function Execution
        │
        ▼
JSON Response
```

---

# Data Processing Helpers

Reusable helper functions standardize backend operations.

### Healthcare Processing Helpers

- Patient Validation
- Appointment Formatting
- Medication Formatting
- Reminder Tracking
- AI Summary Generation
- Dashboard Statistics
- Report Preparation

### Benefits

- Code reusability
- Consistent data formatting
- Easier maintenance
- Improved scalability

---

# Cloud Storage Configuration

Google Sheets acts as the application's cloud database.

### Stored Information

- Patient Name
- Doctor Name
- Appointment Details
- Medication Records
- Reminder Status
- AI Health Summary
- Timestamp
- Healthcare Reports

### Supported Operations

- Create
- Read
- Update
- Delete
- Search
- Statistics
- Reporting

---

# AI Summary Generation

The application integrates with the Groq API using the **llama-3.3-70b-versatile** model.

## AI Processing Steps

1. Retrieve appointment details.
2. Collect visit notes.
3. Retrieve medication information.
4. Build a structured AI prompt.
5. Send the request to the Groq API.
6. Generate a patient-friendly health summary.
7. Validate the generated summary.
8. Store the summary in Google Sheets.
9. Return the summary to the dashboard.

---

# AI Processing Flow

```text
Patient Visit Data
        │
        ▼
Backend Processing
        │
        ▼
Groq API
        │
        ▼
Llama 3.3 70B Versatile
        │
        ▼
Health Summary
        │
        ▼
Google Sheets
```

---

# Twilio SMS Integration

Twilio provides automated reminder notifications.

### Features

- Phone number formatting
- Appointment reminders
- Medication reminders
- SMS delivery tracking
- Reminder history updates

### SMS Workflow

1. Retrieve reminder details.
2. Format recipient phone number.
3. Create reminder message.
4. Send SMS using Twilio.
5. Receive delivery confirmation.
6. Update reminder status.

---

# Google Calendar Integration

Google Calendar integration simplifies appointment scheduling.

### Features

- Generate appointment event links
- Calendar scheduling
- Reminder synchronization
- Appointment management

### Calendar Workflow

1. Retrieve appointment details.
2. Generate Google Calendar event.
3. Create reminder.
4. Display event link.
5. User adds the event to Google Calendar.

---

# Response Validation

Before updating the dashboard, all responses are verified.

### Validation Checks

- Required fields are present.
- Records exist.
- AI summary generated successfully.
- SMS status received.
- Calendar link generated.
- Reports created successfully.

---

# JSON Response Structure

```json
{
  "success": true,
  "appointments": [],
  "medications": [],
  "summary": {},
  "reports": [],
  "status": "Completed"
}
```

---

# Dashboard Workflow

```text
Home Dashboard
      │
      ▼
Add Patient Entry
      │
      ▼
Process Request
      │
      ├──────────────┐
      ▼              ▼
Generate AI     Save to
Summary         Google Sheets
      │              │
      └──────┬───────┘
             ▼
      Update Dashboard
             │
             ▼
      Display Reports
```

---

# Complete Backend Architecture

```text
Frontend (HTML, CSS, JavaScript)
               │
               ▼
Google Apps Script Backend
               │
   ┌───────────┼────────────┐
   │           │            │
   ▼           ▼            ▼
Google Sheets  Groq API   Twilio SMS
 Database      AI Model     Service
   │           │            │
   └───────────┼────────────┘
               ▼
       Google Calendar
               │
               ▼
      RK Health Dashboard
```

---

# Key Features

- Patient record management
- Appointment scheduling
- Medication reminder management
- AI-powered health summaries
- Dashboard analytics
- Healthcare report generation
- Google Sheets cloud storage
- Twilio SMS notifications
- Google Calendar integration
- JSON-based API responses
- Reusable backend helper functions

---

# Security Features

- Input validation
- Data sanitization
- Secure `.env` configuration
- Protected API credentials
- HTTPS communication
- Google authentication
- Twilio credential security
- Cloud data protection

---

# Milestone Outcome

This milestone completes the backend implementation of the RK Health AI Smart Patient Appointment & Medication Reminder System by providing:

- Backend request processing
- CRUD operations for healthcare records
- Google Sheets cloud storage
- AI-powered health summary generation
- Twilio SMS reminder service
- Google Calendar integration
- Dashboard statistics and reporting
- Structured JSON API responses
- Secure and scalable healthcare workflow

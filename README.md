# Cloud Services and Configuration

Before starting development, configure all required cloud services and external accounts.

## Step 1 – Create a Google Account

Create or use an existing Google account to access the following services:

- Google Sheets
- Google Apps Script
- Google Calendar

These services are used for storing patient records, backend automation, and appointment scheduling.

---

## Step 2 – Create a Google Apps Script Project

1. Open Google Apps Script.
2. Click **New Project**.
3. Rename the project to:

```
RK Health AI Reminder System
```

This project hosts backend logic, API endpoints, and integrations with Google Sheets and Google Calendar.

---

## Step 3 – Create Google Sheets Database

Create a Google Spreadsheet named:

```
RK Health Database
```

Create the following sheets:

- Appointments
- MedicationSchedules
- PatientSummaries
- Reports

These sheets will store healthcare records securely.

---

## Step 4 – Configure Twilio Account

Create a Twilio account and collect the following credentials:

- Account SID
- Auth Token
- Twilio Phone Number

These credentials are required to send SMS medication reminders and appointment notifications.

---

## Step 5 – Configure AI Service Access

Generate the required API credentials for AI-powered healthcare summary generation.

For this project, create a Groq API Key and store it securely.

Example:

```
GROQ_API_KEY=your_api_key
```

---

## Step 6 – Secure Configuration

Store all sensitive credentials inside a `.env` file.

Example:

```env
GROQ_API_KEY=your_groq_api_key
TWILIO_ACCOUNT_SID=your_account_sid
TWILIO_AUTH_TOKEN=your_auth_token
TWILIO_PHONE_NUMBER=your_twilio_phone_number
GOOGLE_SHEET_ID=your_google_sheet_id
GOOGLE_SCRIPT_URL=your_google_apps_script_url
```

---

## Security Best Practices

- Never upload `.env` to GitHub.
- Add `.env` to `.gitignore`.
- Never expose API keys in source code.
- Regenerate credentials immediately if they are accidentally exposed.

# Deployment Guide

This section explains how to deploy the RK Health AI Smart Patient Appointment & Medication Reminder System by hosting the frontend on GitHub Pages and publishing the backend as a Google Apps Script Web App.

---

# Frontend Deployment Using GitHub Pages

## Step 1: Create a GitHub Repository

1. Sign in to GitHub.
2. Click **New Repository**.
3. Repository Name:

```text
RK-Health
```

4. Select **Public**.
5. Click **Create Repository**.

---

## Step 2: Upload Project Files

Upload the frontend files:

```text
RK-Health/
│
├── index.html
├── style.css
├── script.js
├── config.js
├── README.md
└── assets/
```

Or use Git:

```bash
git init
git add .
git commit -m "Initial RK Health frontend"
git branch -M main
git remote add origin https://github.com/yourusername/RK-Health.git
git push -u origin main
```

---

## Step 3: Enable GitHub Pages

1. Open your repository on GitHub.
2. Click **Settings**.
3. Select **Pages** from the left menu.
4. Under **Build and deployment**:
   - Source: **Deploy from a branch**
   - Branch: **main**
   - Folder: **/ (root)**
5. Click **Save**.

---

## Step 4: Access the Website

After deployment, your frontend will be available at:

```text
https://username.github.io/RK-Health/
```

Replace **username** with your GitHub username.

---

# Backend Deployment Using Google Apps Script

## Step 1: Open Google Apps Script

1. Open Google Apps Script.
2. Open your RK Health project.

---

## Step 2: Deploy the Web App

1. Click **Deploy**.
2. Select **New Deployment**.
3. Choose **Web App**.
4. Configure:

- Execute as: **Me**
- Who has access: **Anyone** (or **Anyone with the link**, depending on your requirements)

5. Click **Deploy**.

---

## Step 3: Authorize the Project

- Sign in with your Google account.
- Review the requested permissions.
- Click **Allow**.

---

## Step 4: Copy the Web App URL

After deployment, Google Apps Script generates a URL similar to:

```text
https://script.google.com/macros/s/your_script_id/exec
```

Copy this URL for use in the frontend.

---

# Update Frontend Configuration

Open `config.js` and replace the placeholder URL:

```javascript
const CONFIG = {
    SCRIPT_URL: "https://script.google.com/macros/s/your_script_id/exec"
};
```

Save the file and push the updated code to GitHub.

---

# Deployment Workflow

```text
Frontend Files
        │
        ▼
Upload to GitHub
        │
        ▼
Enable GitHub Pages
        │
        ▼
Frontend Website
        │
        ▼
Google Apps Script
        │
        ▼
Deploy as Web App
        │
        ▼
Generate Web App URL
        │
        ▼
Update config.js
        │
        ▼
Frontend Communicates with Backend
```

---

# Deployment Verification

Verify the following after deployment:

- GitHub Pages site opens successfully.
- CSS styles are applied.
- JavaScript loads without errors.
- Forms submit successfully.
- Google Apps Script Web App responds correctly.
- Data is stored in Google Sheets.
- AI summaries are generated.
- Twilio SMS reminders are sent.
- Google Calendar links are created.

---

# Security Best Practices

- Never commit the `.env` file to GitHub.
- Keep Groq API keys and Twilio credentials private.
- Restrict Google Apps Script access where appropriate.
- Use HTTPS URLs for all external services.
- Add `.env` to `.gitignore`.

---

# Technologies Used

- GitHub
- GitHub Pages
- Google Apps Script
- Google Sheets
- Groq API
- Twilio SMS API
- HTML5
- CSS3
- JavaScript (ES6)

---

# Expected Outcome

After completing deployment:

- The frontend is hosted on **GitHub Pages**.
- The backend is deployed as a **Google Apps Script Web App**.
- The frontend communicates with the backend using the Web App URL.
- Patient records are stored in Google Sheets.
- AI summaries are generated using the Groq API.
- SMS reminders are sent through Twilio.
- The RK Health application is fully accessible online.

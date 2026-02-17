# Grade-Level Meeting Form

A clean, Apple-inspired web form for submitting student concerns and grade-wide trends before grade-level meetings.

## 🎯 Features

- **Two Protocol Types:**
  - FAST Protocol (Individual Student Concerns)
  - GRADE Protocol (Grade-Wide Trends)
- **Clean, intuitive interface** inspired by Apple's design
- **Mobile responsive** - works on all devices
- **Direct Google Forms integration** - all submissions automatically saved
- **Independent submission** - teachers can submit either protocol separately

## 🚀 Live Demo

Visit the form: `https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/`

## 📋 Setup Instructions

### 1. Create Two Google Forms

#### Form 1: Individual Student (FAST Protocol)
Create a Google Form with these fields (in this exact order):
1. Your Name (Short answer, Required)
2. Grade Level (Dropdown, Required)
3. Student Name (Short answer, Required)
4. F - Focus (Paragraph, Required)
5. A - Actions Tried (Paragraph, Required)
6. S - Support Needed (Paragraph, Required)
7. T - Talk (Paragraph, Required)
8. Additional Information (Paragraph, Optional)

#### Form 2: Grade Trends (GRADE Protocol)
Create a Google Form with these fields (in this exact order):
1. Your Name (Short answer, Required)
2. Grade Level (Dropdown, Required)
3. G - Group Patterns (Paragraph, Required)
4. R - Red Flags (Paragraph, Required)
5. A - Academics (Paragraph, Required)
6. D - Dynamics (Paragraph, Required)
7. E - External (Paragraph, Required)

### 2. Get Google Forms Entry IDs

For each form:
1. Open your Google Form
2. Click "Send" → Link icon
3. Open the link in a new tab
4. Right-click → "View Page Source"
5. Search for `entry.` to find all entry IDs
6. Write them down in order

### 3. Update the Code

Open `index.html` and update lines 466-492:

**Update Form URLs:**
```javascript
const GOOGLE_FORMS = {
    individual: 'https://docs.google.com/forms/d/e/YOUR_FORM_ID/formResponse',
    trends: 'https://docs.google.com/forms/d/e/YOUR_FORM_ID/formResponse'
};
```

**Update Entry IDs:**
```javascript
const FIELD_MAPPINGS = {
    individual: {
        teacherName: 'entry.YOUR_NUMBER',
        gradeLevel: 'entry.YOUR_NUMBER',
        // ... update all entries
    },
    trends: {
        teacherName: 'entry.YOUR_NUMBER',
        // ... update all entries
    }
};
```

### 4. Deploy to GitHub Pages

1. Create a new repository on GitHub
2. Upload `index.html`
3. Go to Settings → Pages
4. Select "main" branch as source
5. Save and wait 2-3 minutes
6. Your form will be live!

## 📖 Usage

Teachers can:
1. Visit the form URL
2. Choose between FAST or GRADE protocol
3. Fill out the required fields
4. Submit independently

All submissions automatically go to your Google Forms and can be viewed in Google Sheets.

## 🎨 Design

Built with:
- Clean, minimal Apple-inspired design
- Smooth animations and transitions
- Mobile-first responsive layout
- Accessible form controls

## 📝 Meeting Schedule

- 6th & 7th: Every other Tuesday, Period 7
- 8th: Every other Thursday, Period 7
- 9th & 10th: Every other Wednesday, Period 7
- 11th & 12th: Every other Monday, Period 6

## ⚠️ Important

- Submit 48 hours before meetings
- Maximum 6 students per meeting (first submitted, first discussed)
- Include data, not opinions
- Prior conversation with student required

## 🤝 Support

For questions or issues, contact your facilitator or school administration.

---

Created for American School of Recife

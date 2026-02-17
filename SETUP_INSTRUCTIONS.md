# Grade-Level Meeting Form - Setup Guide

## Step 1: Create Google Forms

You need to create TWO separate Google Forms:

### Form 1: Individual Student (FAST Protocol)
1. Go to https://forms.google.com
2. Create a new form
3. Title: "Individual Student Concern - FAST Protocol"
4. Add these questions (all as "Short answer" or "Paragraph" type):
   - Your Name (Short answer, Required)
   - Grade Level (Dropdown: 6th & 7th, 8th, 9th & 10th, 11th & 12th, Required)
   - Student Name (Short answer, Required)
   - F - Focus (Paragraph, Required)
   - A - Actions Tried (Paragraph, Required)
   - S - Support Needed (Paragraph, Required)
   - T - Talk (Paragraph, Required)
   - Additional Information (Paragraph, Optional)

### Form 2: Grade Trends (GRADE Protocol)
1. Create another new form
2. Title: "Grade-Wide Trends - GRADE Protocol"
3. Add these questions:
   - Your Name (Short answer, Required)
   - Grade Level (Dropdown: 6th & 7th, 8th, 9th & 10th, 11th & 12th, Required)
   - G - Group Patterns (Paragraph, Required)
   - R - Red Flags (Paragraph, Required)
   - A - Academics (Paragraph, Required)
   - D - Dynamics (Paragraph, Required)
   - E - External (Paragraph, Required)

## Step 2: Get Google Forms URLs and Entry IDs

For EACH form:

1. Click "Send" button (top right)
2. Click the link icon (<>)
3. Copy the form URL
4. Open the form URL in a new tab
5. Right-click anywhere on the page → "View Page Source"
6. Search (Ctrl+F / Cmd+F) for "entry." 
7. You'll find entries like: `entry.123456789`
8. Write down the entry numbers FOR EACH FIELD IN ORDER

Example of what you're looking for in the source code:
```
"entry.1234567890" - This is for "Your Name"
"entry.0987654321" - This is for "Grade Level"
...etc
```

## Step 3: Update the HTML File

Open `grade-meeting-form.html` and update these sections:

### Update Form URLs (around line 450-453):
```javascript
const GOOGLE_FORMS = {
    individual: 'https://docs.google.com/forms/d/e/YOUR_INDIVIDUAL_FORM_ID/formResponse',
    trends: 'https://docs.google.com/forms/d/e/YOUR_TRENDS_FORM_ID/formResponse'
};
```

**How to get the formResponse URL:**
- Take your form URL: `https://docs.google.com/forms/d/e/1FAIpQLSe.../viewform`
- Replace `viewform` with `formResponse`
- Result: `https://docs.google.com/forms/d/e/1FAIpQLSe.../formResponse`

### Update Field Mappings (around line 456-478):

Replace the placeholder entry numbers with YOUR actual entry numbers:

```javascript
const FIELD_MAPPINGS = {
    individual: {
        teacherName: 'entry.YOUR_ENTRY_NUMBER',      // Replace with actual
        gradeLevel: 'entry.YOUR_ENTRY_NUMBER',       // Replace with actual
        studentName: 'entry.YOUR_ENTRY_NUMBER',      // Replace with actual
        focus: 'entry.YOUR_ENTRY_NUMBER',            // Replace with actual
        actions: 'entry.YOUR_ENTRY_NUMBER',          // Replace with actual
        support: 'entry.YOUR_ENTRY_NUMBER',          // Replace with actual
        talk: 'entry.YOUR_ENTRY_NUMBER',             // Replace with actual
        additional: 'entry.YOUR_ENTRY_NUMBER'        // Replace with actual
    },
    trends: {
        teacherName: 'entry.YOUR_ENTRY_NUMBER',      // Replace with actual
        gradeLevel: 'entry.YOUR_ENTRY_NUMBER',       // Replace with actual
        groupPatterns: 'entry.YOUR_ENTRY_NUMBER',    // Replace with actual
        redFlags: 'entry.YOUR_ENTRY_NUMBER',         // Replace with actual
        academics: 'entry.YOUR_ENTRY_NUMBER',        // Replace with actual
        dynamics: 'entry.YOUR_ENTRY_NUMBER',         // Replace with actual
        external: 'entry.YOUR_ENTRY_NUMBER'          // Replace with actual
    }
};
```

## Step 4: Set Up GitHub Pages

1. Go to https://github.com
2. Click "New Repository" (green button)
3. Name: `grade-level-meeting-form` (or any name you prefer)
4. Make it Public (required for GitHub Pages)
5. Click "Create Repository"
6. Upload your `grade-meeting-form.html` file
7. Rename it to `index.html` (important!)
8. Go to Settings → Pages
9. Under "Source", select "main" branch
10. Click Save
11. Your page will be live at: `https://YOUR-USERNAME.github.io/grade-level-meeting-form/`

## Step 5: Test Your Form

1. Visit your GitHub Pages URL
2. Fill out both forms with test data
3. Check your Google Forms responses to confirm they're arriving correctly
4. If data isn't showing up, double-check your entry numbers

## Troubleshooting

**Form not submitting?**
- Verify your formResponse URLs are correct
- Make sure entry numbers match exactly (case-sensitive)
- Check browser console (F12) for any error messages

**GitHub Pages not working?**
- Make sure file is named `index.html`
- Repository must be public
- Wait 2-3 minutes after enabling Pages

**Data going to wrong fields?**
- Entry numbers must match the ORDER of questions in your Google Form
- Re-check the page source to confirm entry numbers

## Sharing with Teachers

Once everything works:
1. Share your GitHub Pages URL with teachers
2. They can bookmark it for easy access
3. All submissions automatically go to your Google Forms
4. You can view responses in Google Sheets (link in Google Forms)

## Need Help?

If you run into issues:
1. Check that both Google Forms are set to accept responses
2. Verify you're using formResponse (not viewform) in URLs
3. Make sure all entry numbers are correct
4. Test with browser console open (F12) to see errors

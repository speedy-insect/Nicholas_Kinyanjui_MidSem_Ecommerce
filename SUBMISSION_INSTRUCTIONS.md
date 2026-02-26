# Submission Instructions

## GitHub Setup

### Step 1: Create GitHub Repository

1. Go to https://github.com
2. Click "New repository"
3. Repository name: `dsa3050-midsem-powerbi`
4. Description: "DSA 3050A Mid-Semester Exam - Power BI E-Commerce Analysis"
5. Public repository
6. Do NOT initialize with README (we already have one)
7. Click "Create repository"

### Step 2: Push to GitHub

Open terminal in MidSem folder and run:

```bash
git remote add origin https://github.com/YOUR_USERNAME/dsa3050-midsem-powerbi.git
git branch -M main
git push -u origin main
```

Replace `YOUR_USERNAME` with your actual GitHub username.

### Step 3: Verify

1. Go to your GitHub repository
2. Verify all files are uploaded
3. Check that README.md displays correctly
4. Copy the repository URL

---

## PDF Submission

### Create PDF from README

**Option 1: Using Browser**
1. Open README.md on GitHub
2. Print page (Ctrl+P)
3. Save as PDF
4. Name: Nicholas_Kinyanjui_MidSem_BI.pdf

**Option 2: Using Markdown to PDF Tool**
1. Install: `npm install -g markdown-pdf`
2. Run: `markdown-pdf README.md`
3. Rename output to: Nicholas_Kinyanjui_MidSem_BI.pdf

**Option 3: Using Word**
1. Copy README.md content
2. Paste into Word
3. Format properly
4. Add screenshots from screenshots/ folder
5. Save as PDF

---

## Final Submission Checklist

### GitHub Repository
- [ ] Repository created on GitHub
- [ ] All files pushed successfully
- [ ] README.md displays correctly
- [ ] Screenshots folder included
- [ ] Datasets folder included
- [ ] Power BI file included
- [ ] Repository is public

### PDF Document
- [ ] Contains all sections from README
- [ ] Screenshots embedded
- [ ] Power BI link included
- [ ] GitHub link included
- [ ] Student name and ID visible
- [ ] File named correctly
- [ ] File size under 50 MB

### Links to Include

**Power BI Dashboard:**
https://app.powerbi.com/view?r=eyJrIjoiY2M2NTE0MzEtYWNhMC00ODAyLWE0ZDQtYmY0MzU5MTk2OGE3IiwidCI6IjE2ZDgzZWU2LTI1NGEtNDY5ZC1hNmNjLTU0ZTJjYTIzMTNlNyIsImMiOjh9

**GitHub Repository:**
https://github.com/YOUR_USERNAME/dsa3050-midsem-powerbi

---

## What to Submit

Submit ONE PDF containing:
1. Cover page with your details
2. All content from README.md
3. Screenshots embedded in relevant sections
4. Both links (Power BI and GitHub) clearly visible

---

## Folder Structure

Your MidSem folder should contain:

```
MidSem/
├── README.md                  ✓ Main submission document
├── SUBMISSION_INSTRUCTIONS.md ✓ This file
├── .gitignore                 ✓ Git configuration
├── datasets/                  ✓ 5 CSV files
├── powerbi/                   ✓ .pbix file
└── screenshots/               ✓ Evidence images
    ├── dataset_source/
    ├── power_query/
    ├── data_model/
    ├── dashboard/
    └── publishing/
```

---

## Important Notes

1. **Test Power BI link** before submission
2. **Test GitHub link** in incognito browser
3. **Verify all screenshots** are visible
4. **Check file size** of PDF (should be under 50 MB)
5. **Proofread** for typos and errors

---

## Submission Deadline

Check your course portal for exact deadline.

Good luck!

BITS Pilani Digital — Advanced Grading Console
BITS Digital CodeForge V1.0 Submission

A production-grade grading console built for the BITS Digital CodeForge V1.0 challenge. This project takes the original buggy prototype, fixes all identified issues, and reimagines it as a polished, instructor-friendly grading tool.

🌐 Live Demo

Click here to open the app ← replace with your deployed URL

📁 Repository Structure
├── index.html        # Complete single-file application
├── README.md         # This file

The entire application lives in one self-contained index.html file — no build tools, no dependencies to install, no server required.

🚀 Getting Started
Run locally
Clone or download this repository
Open index.html in any modern browser (Chrome, Firefox, Edge, Safari)
That's it — no npm install, no setup
Test file format

Upload an Excel (.xlsx) file with exactly these three column headers:

BITS ID	Course	Total Marks
2024A001	CS F111	82
2024A002	CS F111	71
2024A003	MATH F111	55
Marks must be whole numbers between 0 and 100
Fractional marks (e.g. 80.2) are automatically rounded up
Students to be awarded NC should not be in the file — add them separately in the app
🐛 Stage 1 — Bugs Fixed

13 bugs were identified and fixed in the original prototype:

#	Bug
1	File input only accepted .xls, rejecting .xlsx files
2	Course dropdown duplicated options after a second upload
3	Min and Max stat labels were swapped
4	Stats showed NaN when a course had no students
5	Bell curve did not align with histogram bars
6	Timer displayed 00:00 for the first full second
7	Grade ranges could have gaps/overlaps with no validation
8	Bad rows (invalid marks, blank IDs, duplicates) accepted silently
9	CSV export vulnerable to formula injection
10	Instructor name only validated on course selection, not at export
11	Reset Ranges showed two confirmation dialogs
12	Fractional marks fell between integer boundaries and received no grade
13	File guidance panel overflowed on small screens

See bug_fix_log.pdf for full details on each fix.

🚀 Stage 2 — Enhancements
1. 🔴 Student-Level Preview Table

A live scrollable table at the bottom of the page shows every student's BITS ID, marks, and colour-coded grade badge — updating in real time as cut-offs change. Includes a search box to find a specific BITS ID and a grade filter dropdown.

Why it matters: Instructors can instantly see who is on a grade boundary and make an informed decision before finalizing, instead of relying on aggregate counts alone.

2. 🔴 Relative Grading Mode

A toggle switches the grading panel between Absolute Ranges (set min marks per grade) and Relative Grading (set how many students should receive each grade). In relative mode, cut-offs are calculated automatically from the actual mark distribution. A live counter shows how many students are still unassigned.

Why it matters: BITS Pilani uses relative grading in practice. This mode directly mirrors that workflow instead of forcing instructors to manually calculate where to place cut-offs.

3. 🔴 NC Student List

A text area lets the instructor paste absent student BITS IDs in any format (comma, space, or newline separated). They appear as removable tags and are tracked in a separate NC tab. The final downloaded CSV automatically includes them with grade NC.

Why it matters: The original app had no way to handle NC students at all — the instructor had to manually edit the CSV after downloading. This closes that workflow gap entirely.

4. 🟡 Dark / Light Mode Toggle

A button in the header switches between light and dark themes. The app also respects the system's prefers-color-scheme setting automatically.

5. 🟡 Upload Validation Report

After uploading a file, the app reports how many records loaded, which rows were skipped and why (with row numbers), and how many fractional marks were rounded. Bad rows are never silently accepted.

6. 🟡 Safer CSV Export
Confirmation dialog shows the full grade breakdown before download
CSV filename includes the course name (e.g. CS_F111_grades.csv)
All fields are sanitised against formula injection
7. 🟡 Improved Histogram
Grade cut-off lines drawn directly on the chart with colour-coded labels
Gradient bars with count labels above each bar
Gridlines for easy reading
Bell curve properly scaled and aligned to the bars
8. 🟡 Accessibility & Responsiveness
All inputs have aria-label attributes
Keyboard focus rings on all interactive elements
Layout stacks to single column on mobile (≤820px)
Timer readable by screen readers
🛠️ Tech Stack
Layer	Technology
Language	Vanilla HTML, CSS, JavaScript
Excel parsing	SheetJS (xlsx) v0.18.5 via CDN
Charts	HTML5 Canvas (no library)
Deployment	Static file — works on GitHub Pages, Netlify, Vercel

No frameworks. No build step. One file.

📦 Deployment
Drag and drop index.html
Copy the URL — done
GitHub Pages
Push index.html and README.md to a GitHub repo
Go to Settings → Pages
Set source to main branch, / (root)
Your app is live at https://<username>.github.io/<repo-name>
Vercel
Import the GitHub repo at vercel.com/new
No configuration needed — Vercel detects a static site automatically
📋 Submission Checklist
 Bugs identified and documented
 All bugs fixed
 At least 3 meaningful enhancements added
 Core grading functionality works correctly
 App deployed and accessible via public URL
 Bug Fix Log included (bug_fix_log.pdf)
👤 Author
KAYITHOJU PRAVARAKYA, BITS Digital CodeForge V1.0 — B.Tech AI & ML, CMR College of Engineering and Technology | B.S. Data Science & AI, BITS Pilani

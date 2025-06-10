🛡️ Backup Alerts – Maintenance Plan Setup
📌 Objective
Set up automated full and transactional backups for mission-critical databases using SQL Server Maintenance Plan Wizard in SSMS, ensuring consistency, recoverability, and operational visibility through alerts.

🎯 Target Databases
NGRICAO
NGRMON
AuthorizationApp
NGA_PPA
🛠️ Tools Used
SQL Server Management Studio (SSMS)
SQL Server Agent
Maintenance Plan Wizard
Database Mail (optional, for alerting)
🗂️ Backup Strategy
Backup Type	Frequency	Purpose
Full Backup	Daily (e.g., 1 AM)	Complete recovery base
Transactional Logs	Hourly (e.g., every 30 mins)	Point-in-time recovery support
🧭 Step-by-Step Guide (SSMS GUI)
🔹 A. Full Backup Maintenance Plan
Open SSMS and connect to your instance.
Navigate to SQL Server Agent → Management → Maintenance Plans.
Right-click on Maintenance Plans → Maintenance Plan Wizard.
Click Next ➝ Enter Plan Name: Daily Full Backup.
Choose Single Schedule ➝ Set to run daily at 1:00 AM.
Select the databases:
✅ NGRICAO, NGRMON, AuthorizationApp, NGA_PPA
Choose Back Up Database (Full).
Choose backup directory (e.g., D:\SQLBackups\Full)
➝ Choose compression if available.
Finish the wizard and Save the plan.
🔹 B. Transactional Log Backup Plan
Right-click on Maintenance Plans → New Plan or Wizard.
Name it: Transactional Log Backup.
Schedule it to run every 30 mins.
Select Back Up Database (Transaction Log).
Choose the same databases (must be in Full Recovery Mode).
Set folder path: D:\SQLBackups\Logs
Finish and Save.
📢 Optional: Enable Email Alerts (Highly Recommended)
To notify you of failures:

Set up Database Mail.
Configure an Operator (e.g., your email).
Under SQL Server Agent → Jobs → Right-click your job → Properties → Notifications.
Set: Email Operator on Failure.
🎥 Suggestions for Enhancing this Documentation
You may include:

✅ Screenshots of each wizard step (highly recommended)
📽️ A short video of the setup process (screen recording via Loom, OBS, etc.)
📎 Upload these to your repo or link them from Google Drive
This helps hiring managers or clients visually follow your process even without code.

✅ Result & Impact
Ensures automated, consistent backups of production-critical systems.
Supports disaster recovery and point-in-time restoration.
Reduces dependency on manual backup tasks.
Adds visibility and professionalism to operational database practices.
📂 File Path in Repo
backup-alerts/
├── scripts/  (if needed later)
└── docs/
    └── backup-alerts-overview.md
📬 Questions or Feedback?
Feel free to reach out via email at hauwa.dbtech@gmail.com.

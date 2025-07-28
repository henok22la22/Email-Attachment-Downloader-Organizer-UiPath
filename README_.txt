📧 Email Attachment Downloader & Organizer – UiPath Project
============================================================

📌 DESCRIPTION:
This UiPath automation downloads email attachments from Outlook or Gmail, organizes them into folders by date or sender, and logs all actions. It includes error handling, reusable components, and clear logging for auditing and maintenance.

👤 USE CASE:
Ideal for back-office operations, finance teams, or customer support that receive invoices, orders, or reports via email.

🔧 TECHNOLOGIES & TOOLS USED:
- UiPath Studio (2024.x)
- IMAP or Outlook integration
- System.IO for folder and file operations
- ReFramework-style design principles
- Logging system via text file
- Exception handling with Try-Catch blocks

🧩 WORKFLOW STRUCTURE:
1. **Main.xaml** – Orchestrates the workflow execution.
2. **InitAllSettings.xaml** – Loads configuration and initializes log files.
3. **GetEmailMessages.xaml** – Connects to the email inbox and retrieves messages using IMAP.
4. **ProcessEmailAttachments.xaml** – Loops through emails, downloads attachments, and organizes them into folders.
5. **LogMessage.xaml** – Reusable logging workflow that appends entries to a log file.

📥 INPUT:
- Email account credentials/config (stored securely or in Config.xlsx)
- Subject filter or sender filter (e.g., "Invoice")

⚙️ PROCESS:
1. Load configuration and create log file.
2. Connect to the mailbox via IMAP.
3. Retrieve emails that match subject/sender filter.
4. For each email:
   - If it contains attachments:
     - Create folder (e.g., by date or sender)
     - Save attachments in that folder
     - Log success
   - Else:
     - Log no attachment found
5. Optionally move or mark emails as read
6. Final log output

📤 OUTPUT:
- Files saved in organized folders (e.g., /Attachments/2025-07-22/)
- Log file created per run with timestamped entries

🛡️ ERROR HANDLING:
- All workflows wrapped with Try-Catch blocks
- Errors logged with source and message
- Continue processing even if some emails fail

📁 SAMPLE FILE STRUCTURE:
- /Main.xaml
- /Workflows/
   - InitAllSettings.xaml
   - GetEmailMessages.xaml
   - ProcessEmailAttachments.xaml
   - LogMessage.xaml
- /Logs/YYYY-MM-DD/HH-mm-ss_ExecutionLog.txt
- /Attachments/YYYY-MM-DD/filename.pdf

✅ STATUS: Completed and tested ✅

🧠 NOTES:
- IMAP requires app password for Gmail (enable less secure apps or use OAuth for enterprise).
- Outlook may need account integration via UiPath Assistant.




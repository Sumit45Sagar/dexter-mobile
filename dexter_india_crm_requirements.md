# Software Requirements Specification (SRS) & Application Flow
**Project Name:** DEXTER INDIA CRM Mobile Application  
**Platform:** iOS / Android (Mobile)  

## 1. Introduction
The Dexter India CRM is a comprehensive mobile application suite designed to manage ATM franchise operations, field tasks, and administrative oversight. The system bridges the gap between management, on-ground field executives, and franchise partners through dedicated role-based interfaces.

## 2. User Roles & Access
The application supports three distinct primary user portals, each tailored to specific operational needs:
1.  **Admin & Management:** (Director, Admin, Sub Admin, Finance, Operations) - Focused on oversight, approvals, and analytics.
2.  **Field Team:** (Executive, Sales Officer, Inspector, Project Team) - Focused on task execution, site inspections, and reporting.
3.  **Franchise User:** (Super Master Franchise, Master Franchise, Franchise) - Focused on business tracking, compliance (KYC), and operations.

---

## 3. Application Flow & Functional Requirements

### 3.1 Admin & Management App Flow
**Objective:** Provide top-down visibility, facilitate approvals, and monitor overall business health.

*   **Screen 1: Login**
    *   **Inputs:** Email/Mobile and Password.
    *   **Features:** "Remember me" toggle, Login with OTP option, Forgot Password link.
*   **Screen 2: Admin Dashboard**
    *   **Key Metrics Displayed:** Total Franchises, Active ATMs, Pending Approvals, Open Complaints.
    *   **Visualizations:** ATM Installation Progress bar chart (Site, TIV, Install, Tech Live, Cash Live).
    *   **Navigation:** Bottom tabs (Home, Franchise, Projects, Reports, More).
*   **Screen 3: Franchise Management**
    *   **Features:** Search bar for franchise name/location.
    *   **Filters:** All, Pending, Verified, Approved.
    *   **List View:** Displays Franchise ID, Owner Name, Location, and real-time status tags (e.g., Pending KYC, Under Verification, Approved, Pending Agreement).
*   **Screen 4: Franchise Detail**
    *   **Information Tabs:** Overview, Documents, Agreements.
    *   **Business Details:** Owner Name, Mobile, Email, GST No., Bank Account (masked), KYC Status.
    *   **Actions:** View Documents, Send Reminder.
*   **Screen 5: Project & Installation**
    *   **Features:** Search by ATM ID or Location.
    *   **Filters:** All, In Progress, Completed.
    *   **List View:** Shows ATM ID, Location, current installation stage (e.g., Site Ready, Installation, Tech Live), and a percentage completion progress bar.
*   **Screen 6: Pending Approvals**
    *   **Filters:** All, KYC, Agreement, Finance.
    *   **List View:** Shows items requiring admin action (e.g., KYC Document, GST Document, Bank Details) with a timestamp.
    *   **Actions:** "Review" button for each pending item.
*   **Screen 7: Reports & Analytics**
    *   **Filters:** Company dropdown, Date range (e.g., Last 30 Days).
    *   **Visualizations:** Line charts for "Total Transactions" and Bar charts for "Revenue (₹)". Displays percentage growth/decline.
*   **Screen 8: Notifications**
    *   **Filters:** All, Approvals, Alerts, Updates.
    *   **Alert Types:** New KYC submitted, ATM installation completed, Complaint assigned, GST Bill submitted, Payout processed.

### 3.2 Field Team App Flow
**Objective:** Enable on-ground staff to manage assigned tasks, capture site evidence, and resolve complaints.

*   **Screen 1: Login**
    *   Standard login interface matching the Admin app.
*   **Screen 2: Field Dashboard**
    *   **Header:** Greets user by name (e.g., Field Executive).
    *   **Metrics:** My Tasks, Site Visits, Pending Reports, Open Complaints.
    *   **Today's Schedule:** Timeline view of upcoming tasks with time, task type, and location.
*   **Screen 3: My Tasks**
    *   **Filters:** All, Pending, In Progress, Completed.
    *   **Task List:** Displays Site Visits, Installation Checks, Complaint Visits, and Site Inspections with priority/status tags.
*   **Screen 4: Task Detail**
    *   **Task Info:** ATM ID, Location, Customer Name, Date & Time, Status.
    *   **Checklist:** Interactive checkboxes for Site verification, Electrical readiness, Photos (Exterior/Interior).
    *   **Actions:** "Start Visit" and "Navigate" (Maps integration).
*   **Screen 5: Capture Evidence**
    *   **Tabs:** Photos, GPS, Checklist, Remarks.
    *   **Features:** Visual display of captured images (ATM exterior, interior, etc.).
    *   **Actions:** Add from Gallery or use Camera.
*   **Screen 6: Submit Report**
    *   **Inputs:** Site Status dropdown (e.g., Site Ready), Remarks text area.
    *   **Preview:** Grid of uploaded photos.
    *   **Actions:** "Submit for Review" button.
*   **Screen 7: My Complaints**
    *   **Tabs:** Assigned, In Progress, Completed.
    *   **List View:** Shows Complaint ID, Issue description (e.g., ATM not working, Card not dispensed), Location, and Priority tags (High, Medium, Low).
*   **Screen 8: Task Completion**
    *   **Success Screen:** Green checkmark confirming report submission.
    *   **Actions:** "View Task" or "Back to Home".

### 3.3 Franchise User App Flow
**Objective:** Provide partners with tools to track their ATM performance, manage KYC, and raise operational issues.

*   **Screen 1: Login**
    *   Standard login interface matching the Admin app.
*   **Screen 2: Franchise Dashboard**
    *   **Header:** Greets Franchise Partner by name.
    *   **Metrics:** My Sites, Active ATMs, Pending Documents, Open Complaints.
    *   **Recent Updates:** Feed showing site approvals, payout processing, etc.
*   **Screen 3: My Profile**
    *   **Tabs:** Profile, Documents, Bank & GST.
    *   **Details:** Owner Name, Mobile, Email, GST No., Address.
    *   **Actions:** "Edit Profile" button.
*   **Screen 4: KYC & Documents**
    *   **Document List:** Aadhaar Card, PAN Card, GST Certificate, Bank Statement, Address Proof, Affidavit.
    *   **Status Indicators:** Uploaded, Pending.
    *   **Actions:** View, Upload.
*   **Screen 5: My Sites & Projects**
    *   **Filters:** All, In Progress, Completed.
    *   **List View:** ATM ID, Location, current status, and completion progress bar (similar to Admin view but restricted to own sites).
*   **Screen 6: Submit Operations**
    *   **Tabs:** TXN, CBR/EOD, Loading.
    *   **Inputs:** ATM ID, Date, Total Transactions, Total Amount (₹).
    *   **File Upload:** Upload EOD (End of Day) File.
    *   **Actions:** "Submit" button.
*   **Screen 7: Raise Complaint**
    *   **Inputs:** Category dropdown, ATM ID dropdown, Priority dropdown, Description text area.
    *   **File Upload:** Option to attach photo evidence of the issue.
    *   **Actions:** "Submit Complaint" button.
*   **Screen 8: Finance & Payouts**
    *   **Tabs:** Payout, GST Bills, Statements.
    *   **Summary:** Total Last Payout amount.
    *   **Payout History:** List of previous months with amounts and "Paid" status tags.

---

## 4. Key Non-Functional Requirements
1.  **Security:** Role-based access control (RBAC), OTP verification for secure login, secure document upload handling (KYC data).
2.  **Geolocation:** GPS integration is required for the Field App (Task Navigation and Geo-tagging evidence).
3.  **Media Handling:** Image compression and gallery/camera integration for Field and Franchise apps.
4.  **Real-time Sync:** Status updates made by Field Executives must reflect immediately on Admin and Franchise dashboards.
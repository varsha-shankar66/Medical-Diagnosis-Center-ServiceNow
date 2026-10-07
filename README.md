## 📌 1. Project Overview & Purpose

The **Medical Diagnosis Center by ServiceNow Service Portal** is a specialized healthcare service workflow prototype developed on the **ServiceNow** platform. 

The primary purpose of this solution is to digitize and centralize the patient-facing healthcare journey—replacing fragmented, manual diagnostic request handling with a structured, automated, and end-to-end digital portal. Through this platform, patients can search for diagnostic tests, submit booking requests via a guided 4-stage wizard, track appointment statuses in real time, and securely access medical laboratory reports.

> **Note on Solution Boundaries (from FSD):** The project is implemented using native ServiceNow Service Portal widgets, scoped database tables, and Business Rules. It intentionally operates as a self-contained ServiceNow solution and does not rely on an external React/Node/MongoDB stack or external hospital EHR integrations.

---

## ⭐ 2. Key Features

- **Patient Service Portal Landing Page:** Modern entry point providing quick access to diagnostic test discovery, appointment tracking, and lab report retrieval.
- **Medical Test Catalog:** Searchable and filterable catalog displaying test categories, descriptions, estimated duration, availability, pricing, and a "Book Now" trigger.
- **Guided 4-Stage Appointment Booking Stepper:**
  1. `Details`: Captures patient demographic data (First Name, Last Name, Date of Birth, Gender, Phone, Address).
  2. `Schedule`: Allows selection of preferred date and available appointment time slots.
  3. `Payment`: Processes the configured booking checkout payment stage.
  4. `Done`: Finalizes booking and displays order confirmation details.
- **My Appointments Dashboard:** Provides patients with real-time status tracking (`Scheduled`, `In Progress`, `Completed`, `Rejected`).
- **Automated ServiceNow Business Rules:**
  - `Auto Populate Medical Appointment on Checkout`: Automatically populates patient and test references upon checkout.
  - `Auto Create Report on Appointment Complete`: Instantiates lab report records in the database automatically when an appointment reaches `Completed` status.
  - `rejectionTotalUpdate`: Manages rejection status updates and populates rejection reason audit fields.
- **My Lab Reports Portal:** Secure repository for patients to view and download completed diagnostic test reports.
- **Role-Based Security & Access Control (ACLs):** Enforces data privacy so patients can view only their own records, while administrators and technicians maintain appropriate operational access.

---

## 🛠️ 3. Tech Stack

- **Application Platform:** ServiceNow Enterprise Platform (San Diego / Utah / Washington DC release compatible)
- **Frontend Layer:** Service Portal (AngularJS Widgets, HTML5, Vanilla CSS3, JavaScript ES6)
- **Backend & Logic Layer:** ServiceNow Server-Side JavaScript (GlideRecord API, Business Rules, Workflow Engine)
- **Database Layer:** ServiceNow Scoped Relational Tables (Glide Tables)
- **Security & Authorization:** ServiceNow ACLs (Access Control Lists) & System Roles (`canvas_user`, `admin`, `patient_user`, `lab_technician`)
- **Development Methodology:** Agile Scrum (3 Sprints: Sprint-1 Catalog & Booking, Sprint-2 Schedule & Payment, Sprint-3 Appointments & Reports)

---

## 📁 4. Complete Folder Structure

```text
SERVICENOW/
│
├── 📁 2.REQUIREMENT ANALYSIS/                    # Phase 2: Business & Functional Requirements
│   ├── Customer Journey Map.docx / .pdf          # Patient touchpoint & experience mapping
│   ├── Data Flow Diagrams and User Stories.docx / .pdf # DFD Level 0/1/2 & backlog user stories
│   ├── Solution Requirements.docx / .pdf         # System functional & non-functional requirements
│   └── Technology Stack.docx / .pdf              # ServiceNow platform architectural stack
│
├── 📁 3.PROJECT DESIGN PHASE/                    # Phase 3: System Design & Architecture
│   ├── 📁 Problem Solution/                      # Problem statement & technical solution specs
│   │   ├── Problem - Solution.docx / .pdf
│   │   └── Project Design Phase.docx / .pdf
│   ├── 📁 Proposed Solution/                     # Service Portal layout & design proposal
│   │   ├── Project Design Phase.docx / .pdf
│   │   └── Proposed_Solution Template.docx / .pdf
│   └── 📁 Solution Architecture/                 # ER diagrams & data layer blueprints
│       └── Solution Architecture.docx / .pdf
│
├── 📁 4.PROJECT PLANNING PHASE/                  # Phase 4: Project Management & Backlog
│   ├── Network Request Planning Logic.docx / .pdf # Logic workflow & WBS decomposition
│   └── Network Request Project Planning.docx / .pdf # Product backlog (MDC-1 to MDC-12) & Sprint schedule
│
├── 📁 5.PROJECT DEVELOPMENT PHASE/               # Phase 5: Ideation & Testing Evidence
│   ├── 📁 1.IDEATION PHASE/                      # Problem framing & empathy mapping
│   │   ├── Brainstorming- Idea Generation- Prioritizaation Template.docx / .pdf
│   │   ├── Define Problem Statements Template.docx / .pdf
│   │   └── Empathy Map Canvas.docx / .pdf        # Stakeholder empathy maps
│   ├── 📁 Performance Testing/                   # Test execution & platform verification
│   │   ├── Functional Performance Testing.docx / .pdf # Core workflow load & speed test
│   │   ├── Salesforce Template ServiceNow Equivalent.docx / .pdf # Platform evaluation N/A
│   │   ├── User Acceptance Testing UAT.docx / .pdf # Initial UAT execution test cases
│   │   ├── Artificial Intelligence Model Performance.docx / .pdf (Out of Scope / N/A)
│   │   ├── Machine Learning Model Performance.docx / .pdf (Out of Scope / N/A)
│   │   ├── Power BI Performance.docx / .pdf (Out of Scope / N/A)
│   │   └── Tableau Performance.docx / .pdf (Out of Scope / N/A)
│   └── 📁 User Acceptance Testing/               # Final Release UAT Reports
│       ├── UAT Execution Report.docx / .pdf      # Final test case execution pass matrix
│       └── UAT Report.docx / .pdf                # Release readiness summary
│
├── 📁 6.PROJECT DOCUMENTATION/                   # Phase 6: Specifications & Documentation
│   ├── Final Project.docx / .pdf                 # Comprehensive final project report
│   ├── Functional Specification Document.docx / .pdf # Full technical FSD (Version 1.0)
│   └── README.md                                 # Main Project Documentation README
│
├── 📁 7.PROJECT DEMONSTRATION/                   # Phase 7: Demonstration Guide
│   └── Project Demonstration.docx / .pdf         # Visual guide with step-by-step screenshots
│
└── 📁 WORKFLOW/                                  # End-to-End Workflow Master Reference
    ├── Complete End to End Workflow.docx / .pdf  # 21-page reference workflow document
    └── README.md                                 # Workflow specification README
```

---

## 🎯 5. Purpose of Important Folders and Files

| Folder / File Path | Purpose & Content |
| :--- | :--- |
| **`2.REQUIREMENT ANALYSIS/`** | Contains business requirements, patient journey maps, user stories (MDC-1 to MDC-12), and technology stack specifications. |
| **`3.PROJECT DESIGN PHASE/`** | Houses architectural blueprints, entity-relationship models, and proposed Service Portal wireframes. |
| **`4.PROJECT PLANNING PHASE/`** | Details the 3-Sprint Agile backlog, story point estimations, prioritization matrix, and project schedule. |
| **`5.PROJECT DEVELOPMENT PHASE/`** | Includes ideation empathy maps, functional performance logs, and User Acceptance Testing (UAT) sign-off reports. |
| **`6.PROJECT DOCUMENTATION/`** | Stores the formal **Functional Specification Document (FSD)** and **Final Project Report** defining system behaviors. |
| **`7.PROJECT DEMONSTRATION/`** | Provides screenshot-aligned execution evidence showing every stage of the portal and database flow. |
| **`WORKFLOW/`** | Serves as the master 21-page reference detailing the 11-step end-to-end operational lifecycle. |

---

## 🔄 6. Application / Project Flow

```text
====================================================================================================
                        PATIENT JOURNEY & SERVICENOW WORKFLOW SEQUENCE
====================================================================================================

[ STAGE 1: PORTAL ENTRY ]
  └── Patient logs into Medical Diagnostic Test Center Service Portal
      ├── Views Search Bar & Portal Navigation
      ├── Accesses "Medical Test Catalog"
      ├── Accesses "My Appointments"
      └── Accesses "My Lab Reports"

[ STAGE 2: TEST SELECTION & DISCOVERY ]
  └── Patient browses / searches Diagnostic Test Catalog
      └── Selects desired Diagnostic Test (e.g., Blood Test, MRI, CT Scan)
          └── Views Test Category, Description, Duration & Price -> Clicks "Book Now"

[ STAGE 3: APPOINTMENT BOOKING WIZARD ]
  └── Guided Multi-Step Progress Stepper Widget:
      ├── STEP 1 (Details):  Captures First/Last Name, DOB, Phone, Gender, Address
      ├── STEP 2 (Schedule): Selects Preferred Date & Available Time Slot
      ├── STEP 3 (Payment):  Confirms Booking Payment Checkout
      └── STEP 4 (Done):     Displays Order Confirmation & Unique Appointment Code

[ STAGE 4: SERVICENOW DATA INSERTION & CHECKOUT AUTOMATION ]
  └── Action: Insert Record into APPOINTMENT TABLE (`x_med_appointment`)
      └── Triggers Business Rule: "Auto Populate Medical Appointment on Checkout"
          ├── Links Patient record (`x_med_patient`)
          ├── Maps Diagnostic Test record (`x_med_diagnostic_test`)
          └── Sets Initial Status = "Scheduled"

[ STAGE 5: APPOINTMENT TRACKING ]
  └── Patient visits "My Appointments" Page
      └── Displays live status updates (Scheduled -> In Progress -> Completed)

[ STAGE 6: TEST COMPLETION & REPORT AUTO-GENERATION ]
  └── Medical Staff completes diagnostic test -> Updates Status to "Completed"
      └── Triggers Business Rule: "Auto Create Report on Appointment Complete"
          └── Auto-inserts record into REPORT TABLE (`x_med_report`)
              ├── Assigns Unique Report Number
              ├── Links Patient ID & Appointment Reference
              └── Attaches Medical Diagnostics Summary

[ STAGE 7: PATIENT REPORT ACCESS ]
  └── Patient opens "My Lab Reports" Page
      └── Downloads / Views completed lab results securely
====================================================================================================
```

---

## ⚙️ 7. Installation and Setup

To deploy and run this project on a ServiceNow instance:

1. **Prerequisites:** Access to a ServiceNow instance (San Diego, Utah, or Washington DC release) with `admin` privileges.
2. **Import Update Set:**
   - Log in to ServiceNow as System Administrator.
   - Navigate to **System Update Sets** -> **Retrieved Update Sets**.
   - Click **Import Update Set from XML** and select the scoped application XML package.
   - Click **Preview Update Set**, resolve any instance collisions, and click **Commit Update Set**.
3. **Verify Data Tables:**
   - Confirm table creation under **System Definition** -> **Tables**:
     - `x_med_patient` (`PATIENT TABLE`)
     - `x_med_diagnostic_test` (`DIAGNOSTIC TEST`)
     - `x_med_appointment` (`APPOINTMENT TABLE`)
     - `x_med_report` (`REPORT TABLE`)
4. **Configure Service Portal:**
   - Navigate to **Service Portal** -> **Portals**.
   - Ensure portal URL suffix is configured (e.g., `/sp?id=med_diagnostic_center`).
   - Assign the `med_diagnostic_center_home` page as the default portal homepage.

---

## 🔑 8. Environment Variables & System Configuration

ServiceNow uses platform system properties (`sys_properties`) and scoped application parameters rather than local `.env` files:

- **Instance URL:** `https://<instance-name>.service-now.com`
- **Application Scope Name:** `x_med` (Medical Diagnostic Center)
- **Configured System Roles:**
  - `admin`: Full system access and configuration capabilities.
  - `canvas_user` / `patient_user`: Portal requester role for test booking and report access.
  - `lab_technician`: Healthcare operational role for updating appointment statuses and verifying lab reports.

---

## 🚀 9. How to Run the Project

1. Open your web browser and navigate to your ServiceNow instance portal URL:
   `https://<your-instance>.service-now.com/sp?id=med_diagnostic_center`
2. Log in using a configured patient account or administrator account.
3. Click on **Medical Test Catalog** to browse available diagnostic tests.
4. Select a test and click **Book Now**.
5. Complete the 4-stage booking stepper (**Details** -> **Schedule** -> **Payment** -> **Done**).
6. Navigate to **My Appointments** to verify that the appointment record is created in `Scheduled` status.
7. To test report generation automation:
   - Impersonate a `lab_technician` or `admin`.
   - Open the record in `APPOINTMENT TABLE` and set `Status = Completed`.
   - Re-log as the patient and navigate to **My Lab Reports** to view the auto-generated diagnostic report.

---

## 🗄️ 10. Database Schema & APIs

### Custom Scoped Tables

| Table Name | ServiceNow Table ID | Key Fields & Attributes | Operational Purpose |
| :--- | :--- | :--- | :--- |
| **PATIENT TABLE** | `x_med_patient` | `First Name`, `Last Name`, `DOB`, `Gender`, `Phone`, `Address`, `Created` | Stores master demographic records for patients. |
| **DIAGNOSTIC TEST** | `x_med_diagnostic_test` | `Test Name`, `Category`, `Description`, `Duration`, `Price`, `Availability` | Catalog definition of available medical tests. |
| **APPOINTMENT TABLE**| `x_med_appointment` | `Patient (Ref)`, `Scheduled Date`, `Slot Time`, `Status`, `Rejection Reason` | Core transactional table tracking appointment states. |
| **REPORT TABLE** | `x_med_report` | `Report Number`, `Patient (Ref)`, `Appointment (Ref)`, `Report Date`, `Verified By` | Stores final diagnostic lab report metadata. |

### ServiceNow APIs & Server Scripts Used

- **`GlideRecord` API:** Used in Business Rules for database querying, record insertion, and automated field mapping.
- **Service Portal Server Scripts:** Utilized in custom widgets (`c.server.get()`, `spUtil`) for asynchronous booking validation.

---

## 📦 11. Deployment Instructions

1. **Export Application Scoped Package:** In the development instance, navigate to **Application Repositories** or **Update Sets** and export the application XML.
2. **Target Instance Import:** Import into the Test/Production instance via **Retrieved Update Sets**.
3. **Role Assignment:** Assign `patient_user` and `canvas_user` roles to patient user accounts.
4. **ACL Verification:** Verify row-level ACLs to ensure data segregation across patient accounts.

---

## ⚠️ 12. Known Limitations & Future Improvements

### Known Limitations (Documented in Project Specs)
- **No External EHR/HIS Integration:** The solution does not connect to external hospital electronic health record systems; it relies on ServiceNow tables.
- **No External Stack:** Built natively on ServiceNow; does not use React, Node.js, or MongoDB.
- **Simulated Payment Stage:** The payment stage in the booking stepper is a UI/workflow step without live payment gateway API integration.
- **Out-of-Scope Analytics:** Power BI and Tableau dashboards are documented as N/A (not implemented in the current version).

### Future Improvements
- **Integration Hub APIs:** Connect to external Hospital Information Systems (HIS) via REST/SOAP APIs.
- **Live Payment Gateway:** Integrate Stripe/Razorpay APIs for online card payment processing.
- **Automated Notifications:** Implement SMS/Email alerts via ServiceNow Notification Engine upon appointment status changes.
- **Executive Analytics:** Implement Power BI / Tableau dashboards for lab performance and revenue tracking.

---

## 👥 Authors & Acknowledgments

- **Project Name:** Medical Diagnosis Center by ServiceNow Service Portal
- **Platform:** ServiceNow
- **Document Date:** October 06, 2026
- **Version:** 1.0 (Release Ready / UAT Passed)

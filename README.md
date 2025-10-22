# 🍕 CANN Pizzeria - Comprehensive Management System

A **full-stack information system** for a local pizza business, built on **Zoho Creator**.  
This end-to-end solution automates core business processes — **CRM, order management, inventory control, HR scheduling,** and **financial tracking** — developed through synchronized teamwork to eliminate manual errors and maximize efficiency.

---

## 📦 Our Solution & System Architecture

The system replaces manual, error-prone operations with an integrated **Zoho Creator application** based on a **relational database**.  
Dynamic workflows ensure that an action in one module automatically updates related data across the platform.

---

## ⚙️ Core Workflows

### 1. Dynamic Order & Inventory Automation

A **closed-loop inventory system** manages stock from purchase to sale.

- **Smart Order Forms:**  
  Real-time filtering connects *Menu* and *Recipes* with *Inventory*, only showing items possible with current stock.
- **Cumulative Stock Validation:**  
  Before order submission, an `"On-Validate"` script aggregates total ingredient demand and checks stock availability.  
  Prevents overselling or depleting shared ingredients.
- **Automated Stock Ledger:**  
  - **Deduction (On-Success):** Automatically reduces ingredient quantities when orders are placed.  
  - **Addition (Custom Function):** Increases stock when managers confirm supplier deliveries via the "Receive Order" button.
- **Proactive Alerts:**  
  Automatic email notifications trigger when stock drops below *safety_stock* thresholds.

---

### 2. Intelligent HR & Smart Scheduling

A **dynamic HR module** ensures accuracy in staff scheduling and availability.

- **Dynamic Staff Filtering:**  
  - Displays only *Active* employees.  
  - Hides those marked *Absent* for specific shifts.  
  - Prevents duplicate assignments.
- **Minimum Staff Validation:**  
  Ensures every Shift Type meets required staffing (e.g., 2 Cooks + 1 Driver).  
  Shifts cannot be saved unless this validation passes.
- **Automated Communication:**  
  A scheduled workflow (`Send_Employee_Roster_For_`) emails the next week’s roster to all active employees every Saturday night.

---

### 3. Automated Financial Ledger & BI

The system features a **hands-off financial ledger** automatically populated by system events and visualized via a BI dashboard.

- **Automated Transaction Logging:**  
  The `Finance_Records` table serves as a read-only source of truth.
  - **Income:** Logged when customer orders are received.  
  - **COGS Expense:** Logged upon supplier stock receipt.  
  - **Payroll Expense:** Calculated monthly by the scheduled `Calc_Monthly_Salary` job (total hours × hourly_rate).
- **Management Dashboard:**  
  Built in **ZML**, offering KPIs, charts, and reports such as:  
  - *Low Stock Items*  
  - *Returning vs. New Customers*

---

## 🧩 Key Technical Challenges & Solutions

- **Public vs. Private Menu:**  
  - *Challenge:* Show recipe details to employees but hide them from customers.  
  - *Solution:* Created a separate public-facing page with customer-safe fields (name, image, price).

- **Syncing Absences to Shifts:**  
  - *Challenge:* Difficult to link Absence DateTime with Shift Date + Time.  
  - *Solution:* Rebuilt Absences form using a Date field and a multi-select lookup to `Shifts_Types`.  
    Allows consistent availability checks (e.g., *“Absent for Morning shift on 2025-10-22”*).

---

## 🧠 Technology Stack

- **Platform:** Zoho Creator (Low-Code)
- **Language:** Deluge (for workflows, automation, and scheduling)
- **Dashboard UI:** ZML (Zoho Markup Language)

---

## 👨‍💻 Project Team

- Chen Biazi  
- Noa Ezri  
- Niv Mairovich  
- Alon Achitov  

**Project Grade:** 100  
**Note:** This project was built using an **academic free license** of Zoho Creator.  
Due to licensing restrictions, it was not possible to share a public link for live system demonstration or viewing.  
However, **detailed screenshots of different application pages** are available in the **System Manual PDF** attached to this project repository.

---

## 💡 Summary

CANN Pizzeria’s system transforms manual operations into an intelligent, automated platform that synchronizes **orders, inventory, staff management,** and **finance**, delivering efficiency, accuracy, and real-time insight across the business.

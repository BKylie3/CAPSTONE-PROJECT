# ✈️ Trip Reservation System – Oracle PL/SQL Capstone Project

This project is a **Trip Reservation System** designed for the **travel and tourism industry** that will help users to independently book flights and hotel accommodations online without needing traditional travel agents.
The project was designed in multiple phases to reflect real-world business processes and that will emphasize on improving booking accuracy, user convenience, and operational efficiency.

---

## 📁 File Naming Format

**Filename:** `Wed_27109_Kylie_TripReservationSystem_DB`  
**Developer:** Belishya Rurangwa Kylie  
**Course:** PLSQL – Capstone Project

---

## 📌 Phase 1: Problem Statement and Presentation

### 🔍 Problem Definition
Traditional travel booking methods involve long processes, manual errors, and high dependency on agents. Customers face delays and administrators struggle with reconciliation.

### 🧭 Context
Used in the **travel and tourism industry**, the system enables **independent booking** of flights and accommodations via an online interface.

### 👥 Target Users
- Independent travelers  
- Travel agencies  
- System administrators  

### 🎯 Project Goals
- Automate booking workflows  
- Improve accuracy of trip reservations  
- Reduce administrative load  
- Enhance customer satisfaction  

### 📦 Entities
- **Customers**
- **Trips**
- **Transport**
- **Accommodations**
- **Bookings**

### ✅ Anticipated Benefits
- Self-service access  
- Real-time availability  
- Fewer errors and no double-bookings  
- Centralized trip tracking  

---

## 📊 Phase 2: Business Process Modeling (MIS)

### 📌 Scope
The system models a **trip booking** workflow with a focus on customer interaction, staff involvement, and system automation. It supports MIS by improving **operational efficiency** and enabling **data-driven decisions**.

### 🧩 Key Entities and Roles
- **Customer**: Searches and books trips
- **System**: Checks availability, processes bookings
- **Administrator**: Monitors and audits reservations

### 🛠 Swimlanes Used
Each actor (Customer, System, Admin) is assigned a lane in the **BPMN diagram** for process clarity.

### 🔄 Logical Flow
1. Search trip  
2. Check transport/accommodation availability  
3. Reserve if available  
4. Make payment  
5. Admin logs confirmation  

![Project 2](https://github.com/user-attachments/assets/e00c8594-3744-4467-af0d-3c805295df95)


---

## 🗂 Phase 3: Logical Model Design

### 🧱 Entities & Attributes
- **CUSTOMER**: Customer_ID, Name, Email, Phone  
- **TRIP**: Trip_ID, Destination, Duration, Price  
- **TRANSPORT**: Transport_ID, Type, Departure_Time, Price  
- **ACCOMMODATION**: Accom_ID, Room_Type, Price_Per_Night  
- **BOOKING**: Booking_ID, Customer_ID (FK), Trip_ID (FK), Payment_Status  

### 🔗 Relationships
- One customer → many bookings  
- One trip → many bookings  
- One transport/accommodation → many trips  

### 📏 Constraints
- `NOT NULL`, `PRIMARY KEY`, `FOREIGN KEY`, `CHECK`, `UNIQUE`

### 🧹 Normalization
- Ensured 3rd Normal Form (3NF)  
- Removed redundancy and ensured referential integrity

![Project 3](https://github.com/user-attachments/assets/6040d37f-28fe-455f-9a50-c9336de54449)

---

## 💾 Phase 4: Database Creation (PDB)

### 🛠 Database Setup
- **Database Name**: `Wed_27109_Kylie_TripReservationSystem_DB`
- **Username**: `Kylie`
- **Password**: `Kylie`
- **Privileges**: All admin privileges assigned

### 🖥 OEM Monitoring
- Set up via **Oracle Enterprise Manager (OEM)**  
- Screenshots included to verify:
  - PDB creation
  - Table deployment
  - Relationships

---

## 🧪 Phase 5: Table Implementation & Data Insertion

This phase focused on converting the logical data model into a physical Oracle database by creating tables, inserting test data, and enforcing data integrity for reliable operations.

### 1. Table Creation
- Tables (`Customer`, `Trip`, `Transport`, `Accommodation`, `Booking`) were created based on the ERD.
- Each table includes appropriate columns, data types, and constraints.

### 2. **Data Insertion**
- Realistic sample records were inserted to simulate real-world booking scenarios.
- Data included multiple trips, transport modes, room types, and booking statuses.

### 3. **Data Integrity**
- Enforced via:
  - **Primary Keys**: Uniqueness of records
  - **Foreign Keys**: Relationship enforcement
  - **Constraints**: `NOT NULL`, `UNIQUE`, and `CHECK` for value validation

### 4. **Physical Database Structure**
- Fully implemented and normalized
- Indexed and optimized for query performance
- Designed to support the system’s booking, tracking, and reporting functions

---

## 📈 Outcome

- A fully functional, relational database schema ready for transaction processing, user interaction, and advanced logic in future phases.

---

## 🔄 Phase 6: Database Interaction and Transactions  

This phase focused on enhancing system functionality through SQL operations, procedural logic, and modular programming using Oracle PL/SQL.

### 1. **DML & DDL Operations**
- Performed `INSERT`, `UPDATE`, `DELETE`, `ALTER`, and `DROP` on core tables like `Booking`, `Trip`, and `Customer`.

### 2. **Problem Statement & Analysis**
- Identified the need to track trip booking frequency and calculate total revenue per trip.
- Used `GROUP BY` and PL/SQL logic to analyze bookings.

### 3. **Procedures & Functions**
- Created procedures (e.g., `Show_Customer_Bookings`) to display customer-specific data.
- Built functions (e.g., `Calculate_Trip_Revenue`) to compute total revenue per trip.

### 4. **Cursors & Exception Handling**
- Used cursors to loop through pending bookings.
- Applied exception handling to prevent runtime errors.

### 5. **Packages**
- Grouped reusable procedures/functions in a package (`Booking_Pkg`) to confirm bookings and check statuses.

---

## 📈 Outcomes

- Enhanced data interaction using modular PL/SQL.
- Improved error management and data consistency.
- Enabled reusable logic through packages for future scalability.

---

## 🔐 Phase 7: Advanced Database Programming and Auditing  

This phase focused on strengthening system security, automation, and accountability using advanced PL/SQL features like triggers, packages, and auditing mechanisms.

### ✅ Key Activities

#### 1. **Problem Statement**
- The system needed to restrict table modifications during weekdays and public holidays.
- Goal: Prevent unauthorized changes and track all sensitive operations.

---

#### 2. **Trigger Implementation**
- **Simple Triggers**: Blocked `INSERT`, `UPDATE`, and `DELETE` on weekdays.
- **Holiday Restriction**: Used a `Holiday_List` table to block changes during defined holiday dates.
- **Logic**: Trigger checks system day and holiday dates before allowing any DML operation.

---

#### 3. **Auditing & Access Control**
- Created an `Audit_Log` table to capture:
  - `User_ID`, `Action`, `Date_Time`, and `Status` (Allowed/Denied)
- Logged all booking-related operations through triggers.
- Used **functions and packages** to automate and track audit entries.

---

### 🔐 Outcomes

- Enhanced system security by restricting DML operations on sensitive days.
- Achieved full traceability of user actions.
- Improved accountability through centralized audit logging.

---

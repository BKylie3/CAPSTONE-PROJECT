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

📸 *Visual diagrams included in `/diagrams` folder*

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

### 📐 1. Table Creation
Tables created using `CREATE TABLE` scripts aligned with logical model.

#### Example: `Customer`
```sql
CREATE TABLE Customer (
  Customer_ID NUMBER PRIMARY KEY,
  Name VARCHAR2(100) NOT NULL,
  Email VARCHAR2(100) UNIQUE NOT NULL,
  Phone VARCHAR2(15),
  Preferences CLOB
);
###📥 2. Data Insertion
INSERT INTO Booking (
  Booking_ID, Customer_ID, Trip_ID, Booking_Date, Payment_Status)
VALUES 
(1001, 1, 301, TO_DATE('2024-12-01', 'YYYY-MM-DD'), 'Pending');


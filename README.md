# 🛡️ PPE Inventory Management System for Healthcare

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

A Python-based inventory management system designed for tracking Personal Protective Equipment (PPE) during COVID-19 🦠, featuring multi-user access controls, transaction logging, and real-time inventory tracking 📦.

---

## 📚 Table of Contents
1. [🧾 Project Overview](#-project-overview)
2. [✨ Key Features](#-key-features)
3. [🧩 System Architecture](#-system-architecture)
4. [📊 Data Structures](#-data-structures)
5. [⚙️ Core Functionalities](#-core-functionalities)
6. [💻 Installation](#-installation)
7. [🚀 Usage](#-usage)
8. [🖼️ Screenshots](#-screenshots)
9. [🔍 Technical Details](#-technical-details)
10. [📄 License](#-license)

---

## 🧾 Project Overview

**Purpose**:  
Developed to help healthcare organizations manage critical PPE supplies across **3 hospitals** and **3 suppliers** during the COVID-19 pandemic.

**Main Features**:
- 📦 Real-time inventory tracking (box-level)
- 👥 Role-based access (Hospitals vs Suppliers)
- 🕒 Audit logging with timestamps
- 🧾 Automated reporting module

**Tech Stack**:
- 🐍 Pure Python (no external libraries)
- 📁 File-based storage (CSV-style)
- 🖥️ Console interface

---

## ✨ Key Features

### 📦 Inventory Management

| Feature         | Description                                          |
|-----------------|------------------------------------------------------|
| ➕ Add Items     | Suppliers can add stock with validation              |
| ➖ Remove Items  | Hospitals withdraw stock with safety checks          |
| ⚠️ Stock Alerts | Alerts when PPE levels fall below 25 boxes           |

---

### 🔒 Security Controls
```python
# Input validation example
while not valid:
    item_code = input("Enter item code: ")
    if item_code in VALID_CODES:
        valid = True
    else:
        print("Invalid code!")
```

---

## 🧩 System Architecture

### 📈 Data Flow
```
Suppliers → [Add Stock] → PPE.txt
Hospitals → [Withdraw Stock] → Distribution.txt
                                ↘→ hospitals.txt
```

### 📁 File Structure
```
├── main.py              # Main program logic
├── ppe.txt              # Current PPE inventory
├── hospitals.txt        # Hospital stock records
├── supplier.txt         # Supplier contributions
└── distribution.txt     # Complete transaction history
```

---

## 📊 Data Structures

**PPE.txt Example**
```
HC,Head Cover,100
FS,Face Shield,150
MS,Medical Suit,75
```

**hospitals.txt Example**
```
HOS11,Hospital 1,50,30,20,0,15,10
HOS22,Hospital 2,30,45,10,5,20,5
```

---

## ⚙️ Core Functionalities

### 1. 🔁 Update Inventory
```python
def update_inventory():
    while True:
        print("\n1. Add Items\n2. Take Items\n3. Back")
        choice = input("Select operation: ")
        if choice == "1":
            add_items()
        elif choice == "2":
            remove_items()
```

### 2. 🔍 Search System
- Search by supplier, hospital, or item code  
- Returns complete transaction history

### 3. 📊 Reporting Module
```python
def generate_report():
    print("\n1. Sorted Inventory\n2. Low Stock Items")
    choice = input("Select report type: ")
    if choice == "1":
        print_sorted_inventory()
```

---

## 💻 Installation

### Requirements:
- Python 3.x ✅  
- No additional packages required

### Setup:
```bash
git clone https://github.com/yourusername/ppe-inventory.git
cd ppe-inventory
```

### Initialize Sample Data:
```python
with open("ppe.txt", "w") as f:
    f.write("HC,Head Cover,100\nFS,Face Shield,100\nMS,Medical Suit,100")
```

---

## 🚀 Usage

### Run the Program:
```bash
python main.py
```

### 🧭 Main Menu:
```
1. Update Inventory
2. Search
3. Print Report
4. Exit
```

### ✅ Sample Workflow:

**Supplier adds 50 face shields**
```
Enter item code: FS
Enter supplier code: SUP11
Enter quantity: 50
```

**Hospital withdraws 20 face shields**
```
Enter hospital code: HOS22
Enter item code: FS
Enter quantity: 20
```

---

## 🖼️ Screenshots

**Main Menu UI**
```
(1) Update Inventory
(2) Search
(3) Print Report
(4) Exit
Choice: _
```

**Sample Inventory Report**
```
HC: 85
FS: 130
MS: 95
GL: 45 (LOW STOCK)
```

---

## 🔍 Technical Details

### ✅ Validation Logic
- Item Codes: `HC`, `FS`, `MS`, `GL`, etc.
- Supplier Limits:
  - SUP11 ➜ HC, FS  
  - SUP22 ➜ MS, GL  
- Hospital cannot withdraw more than available

### 📅 Date Handling
```python
from datetime import date
today = date.today()
dist_file.write(f"{supplier},{item},{qty},{today}")
```

---

## 📄 License

📝 **MIT License** — Free to use for education and commercial projects.  
See the [LICENSE](./LICENSE) file for full details.

---

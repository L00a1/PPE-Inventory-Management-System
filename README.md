PPE Inventory Management System
A Python-based solution for tracking medical supplies during COVID-19

📌 Project Overview
Developed to help healthcare organizations manage Personal Protective Equipment (PPE) inventory during the pandemic, this system tracks supplies across multiple hospitals and suppliers with secure access controls and automated reporting.

✨ Key Features
Inventory Management
Add/remove PPE items (6 supported types)
Track stock levels across 3 hospitals
Record distributions with timestamps

Data Security
Role-based access control
Input validation for all transactions
Audit logs for accountability

Reporting
Low stock alerts (<25 boxes)
Sort inventory in ascending order
Generate supplier/hospital-specific reports

🛠️ Technical Implementation
def update_inventory():
    # Handles adding/removing items
    # with input validation
    ...

def generate_report():
    # Creates inventory summaries
    # with sorting/filtering
    ...
Data Storage:
Text-file based system (CSV-like structure)
Separate files for:
Current inventory (ppe.txt)
Supplier records (supplier.txt)
Transaction logs (distribution.txt)

🚀 Getting Started
Clone the repository
Run main.py
Use menu to:
Update inventory
Search records
Generate reports

📊 Sample Output
(1) Update Inventory
(2) Search
(3) Print Report

Choice: 1
-> Added 50 face masks (SUP11)
-> Logged to distribution.txt

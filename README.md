# PPE Inventory Management System

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![License](https://img.shields.io/badge/License-MIT-green)

A secure inventory tracking system for medical supplies during COVID-19, built with Python.

## 📋 Table of Contents
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Installation](#-installation)
- [Usage](#-usage)
- [File Structure](#-file-structure)
- [Screenshots](#-screenshots)
- [License](#-license)

## ✨ Features
| Category        | Functionality                          |
|-----------------|----------------------------------------|
| **Inventory**   | Add/remove PPE items                   |
|                 | Track stock across 3 hospitals         |
| **Security**    | Role-based access control              |
|                 | Comprehensive input validation         |
| **Reporting**   | Low stock alerts (<25 boxes)           |
|                 | Historical transaction logs            |

## 💻 Tech Stack
- **Core**: Python 3.x (No external dependencies)
- **Data Storage**: 
  ```plaintext
  ppe.txt - Current inventory
  supplier.txt - Supplier records
  distribution.txt - Audit logs

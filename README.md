# Cinema Tickets Booking System - Database Design

![Database Schema](ER%20Diagram.jpg)

## 📋 Overview

A relational database management system for cinema ticket booking operations. This project implements a normalized database schema to manage theaters, movie screenings, ticket reservations, and customer information.

**Academic Project** | Database Management Systems  
**Developer:** Ahtisham  
**Institution:** GC University Lahore

---

## ✨ Features

- User registration and management
- Multiple theater and screen support
- Movie catalog with genre classification
- Show scheduling with dynamic pricing
- Seat availability tracking (Gold/Silver classes)
- Booking and payment management
- Individual ticket generation

---

## 🗄️ Database Schema

### Tables

1. **Web_User** - Customer information
2. **Theatre** - Cinema locations
3. **Screen** - Theater halls with seating capacity
4. **Movie** - Film catalog
5. **Show** - Screening schedules
6. **Booking** - Reservation records
7. **Ticket** - Individual ticket details

### ER Diagram

![ER Diagram](ER%20Diagram.jpg)

---

## 🚀 Getting Started

### Prerequisites
- MySQL 8.0+ or SQL Server
- MySQL Workbench / SQL Server Management Studio

### Installation

1. **Create Database**
```sql
CREATE DATABASE cinema_booking_system;
USE cinema_booking_system;
```

2. **Run Setup Scripts**
   - Execute SQL from `Table creation and insertion.txt`
   - Tables will be created with sample data

3. **Test Queries**
   - Run queries from `queries.txt` to verify setup

---

## 📊 Sample Queries

### Revenue Analysis by Movie
```sql
SELECT Name, Total_Revenue
FROM (SELECT Movie_ID, SUM(Total_cost) AS Total_Revenue
      FROM Show AS s
      INNER JOIN Booking AS b ON s.Show_ID = b.Show_ID
      GROUP BY Movie_ID) AS m
INNER JOIN Movie ON m.Movie_ID = Movie.Movie_ID
ORDER BY Total_Revenue DESC;
```

### User Booking History
```sql
SELECT First_name, Last_name, Email_ID, Phone_number, Card_number 
FROM Web_User AS wu
INNER JOIN Booking AS b ON wu.Web_User_ID = b.User_ID;
```

### Theater-Screen Mapping
```sql
SELECT Name_of_Theatre, Area, Screen_ID
FROM Theatre AS t
LEFT JOIN Screen AS s ON t.Theatre_ID = s.Theatre_ID;
```

**More queries available in `queries.txt`**

---

## 📂 Project Files

- `ER Diagram.jpg` - Visual database schema
- `queries.txt` - 6 sample SQL queries
- `Table creation and insertion.txt` - DDL & DML scripts
- `ticketproject.docx` - Complete documentation

---

## 🛠️ Tech Stack

- **Database:** MySQL / SQL Server
- **Design:** ER Modeling, 3NF Normalization
- **Tools:** MySQL Workbench, SQL Server Management Studio

---

## 👨‍💻 Author

**Ahtisham** - [@smokhood](https://github.com/smokhood)

📧 ahtishamravian206@gmail.com  
🎓 GC University Lahore

---

## 📄 License

Educational project for Database Management Systems coursework.

---

**⭐ Star this repository if you find it helpful!**

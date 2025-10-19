# student-performance-sql-project
SQL project analyzing student performance and academic insights using MySQL
# 🎓 Student Performance Database Analysis using SQL

## 📘 Overview
This project demonstrates how to design and analyze a **student performance database** using **MySQL**.  
It includes tables for students, subjects, marks, and attendance — and performs SQL queries to extract meaningful academic insights such as top-performing students, subject averages, and attendance correlations.

---

## 🧱 Database Design
The database consists of **four main tables**:

| Table Name | Description |
|-------------|--------------|
| `Students` | Contains student details like ID, name, gender, class, and age |
| `Subjects` | Contains subject names and their IDs |
| `Marks` | Records marks obtained by each student in each subject |
| `Attendance` | Tracks total classes and classes attended by each student |

---

## 🗃️ SQL Files in This Project
| File | Purpose |
|------|----------|
| `create_database.sql` | Defines database schema and table creation |
| `insert_data.sql` | Inserts sample records into all tables |
| `queries_analysis.sql` | Contains all analytical SQL queries |
| `conclusions.txt` | Summarizes final insights and findings |

---

## 🧠 Key SQL Concepts Used
- **Database Design (DDL):** `CREATE`, `ALTER`, `DROP`
- **Data Manipulation (DML):** `INSERT`, `UPDATE`, `DELETE`
- **Joins:** `INNER JOIN`, `LEFT JOIN`
- **Aggregations:** `AVG()`, `COUNT()`, `SUM()`
- **Clauses:** `GROUP BY`, `ORDER BY`, `LIMIT`
- **Subqueries & Aliasing**

---

## 📊 Example Analytical Queries

### 🔹 1. Average Marks of Each Student
```sql
SELECT s.student_name, AVG(m.marks_obtained) AS avg_marks
FROM Students s
JOIN Marks m ON s.student_id = m.student_id
GROUP BY s.student_name
ORDER BY avg_marks DESC;

---

### 🔹 2. Top 3 Students by Average Marks
```sql
SELECT s.student_name, AVG(m.marks_obtained) AS average_marks
FROM Students s
JOIN Marks m ON s.student_id = m.student_id
GROUP BY s.student_name
ORDER BY average_marks DESC
LIMIT 3;
SELECT s.student_name,
       (a.classes_attended * 100 / a.total_classes) AS attendance_percentage,
       AVG(m.marks_obtained) AS average_marks
FROM Students s
JOIN Attendance a ON s.student_id = a.student_id
JOIN Marks m ON s.student_id = m.student_id
GROUP BY s.student_name
ORDER BY average_marks DESC;

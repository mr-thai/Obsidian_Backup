# 1. SELECT – Truy vấn dữ liệu

## 1.1 `SELECT * FROM table;`  
## 1.2 Chọn cột: `SELECT col1, col2 …`  
## 1.3 Alias: `AS` (cột & bảng)  
## 1.4 DISTINCT  
## 1.5 WHERE với toán tử: `=, <>, >, <, BETWEEN, LIKE, IN, IS NULL`  
## 1.6 ORDER BY (ASC, DESC)  
## 1.7 LIMIT / OFFSET (hoặc TOP / FETCH FIRST tùy DBMS)

---

# 2. Hàm & Biểu thức

## 2.1 Hàm tổng hợp: `COUNT(), SUM(), AVG(), MIN(), MAX()`  
## 2.2 GROUP BY  
## 2.3 HAVING  
## 2.4 Hàm chuỗi: `CONCAT(), SUBSTRING(), LENGTH(), UPPER(), LOWER(), TRIM()`  
## 2.5 Hàm số học: `ROUND(), CEIL(), FLOOR(), MOD(), POWER()`  
## 2.6 Hàm ngày giờ: `NOW(), CURRENT_DATE, DATE_ADD(), DATE_DIFF(), EXTRACT()`  
## 2.7 Xử lý NULL: `COALESCE(), NULLIF()`  
## 2.8 Biểu thức điều kiện: `CASE WHEN … THEN … ELSE … END`

---

# 3. DML – Data Manipulation Language

## 3.1 INSERT INTO … VALUES …  
## 3.2 INSERT nhiều dòng một lệnh  
## 3.3 INSERT SELECT (chèn từ kết quả truy vấn)  
## 3.4 UPDATE … SET … WHERE …  
## 3.5 DELETE FROM … WHERE …  
## 3.6 UPSERT / MERGE (tùy DBMS, cú pháp khác nhau)

---

# 4. DDL – Data Definition Language

## 4.1 CREATE TABLE (cột + kiểu dữ liệu)  
## 4.2 ALTER TABLE  
### 4.2.1 ADD COLUMN  
### 4.2.2 DROP COLUMN  
### 4.2.3 RENAME COLUMN  
### 4.2.4 MODIFY (đổi kiểu dữ liệu)  
## 4.3 DROP TABLE  
## 4.4 TRUNCATE TABLE

---

# 5. Constraints – Ràng buộc dữ liệu

## 5.1 PRIMARY KEY  
## 5.2 FOREIGN KEY + ON DELETE/ON UPDATE CASCADE  
## 5.3 NOT NULL  
## 5.4 UNIQUE  
## 5.5 DEFAULT  
## 5.6 CHECK (giới hạn giá trị)

---

# 6. JOIN & Subquery

## 6.1 INNER JOIN  
## 6.2 LEFT JOIN / RIGHT JOIN  
## 6.3 FULL OUTER JOIN  
## 6.4 SELF JOIN  
## 6.5 CROSS JOIN (tích Descartes)  
## 6.6 UNION / UNION ALL  
## 6.7 INTERSECT / EXCEPT (tùy DBMS)  
## 6.8 Subquery trong:  
###  6.8.1 SELECT  
###  6.8.2 FROM (derived table)  
### 6.8.3 WHERE (IN, EXISTS)  
## 6.9 CTE: `WITH alias AS (SELECT …)`

---

# 7. Transaction (TCL)

## 7.1 BEGIN / START TRANSACTION  
## 7.2 COMMIT  
## 7.3 ROLLBACK  
## 7.4 SAVEPOINT  
## 7.5 SET TRANSACTION ISOLATION LEVEL  
	Read Uncommitted  
	Read Committed  
	Repeatable Read  
	Serializable

---

# 8. Index & Query Optimization

## 8.1 CREATE INDEX idx_name ON table(col)  
## 8.2 DROP INDEX idx_name  
## 8.3 UNIQUE INDEX  
## 8.4 Composite Index (nhiều cột)  
## 8.5 EXPLAIN / EXPLAIN ANALYZE

---

# 9. Stored Objects

## 9.1 VIEW: `CREATE VIEW … AS SELECT …`  
## 9.2 Stored Procedure: `CREATE PROCEDURE …`  
## 9.3 Function: `CREATE FUNCTION …`  
## 9.4 Trigger: BEFORE/AFTER INSERT, UPDATE, DELETE

---

# 10. Advanced SQL

## 10.1 Window Functions (OVER):  
### 10.1.1 ROW_NUMBER(), RANK(), DENSE_RANK()  
### 10.1.2 SUM() OVER (PARTITION BY … ORDER BY …)  
## 10.2 Pivot / Unpivot (xoay bảng – tùy DBMS)  
## 10.3 Recursive CTE (`WITH RECURSIVE …`)  
## 10.4 CASE nâng cao (nested conditions)  
## 10.5 EXISTS vs NOT EXISTS  
## 10.6 Common Patterns:  
### 10.6.1 Top N per group  
### 10.6.2 Running total  
### 10.6.3 Gaps and islands

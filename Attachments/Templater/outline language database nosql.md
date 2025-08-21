## **1. Kết nối & Khởi tạo**

- Kết nối DB (CLI, shell, driver).
    
- Tạo database: `use myDB`.
    
- Tạo collection: `db.createCollection("users")`.
    
- Liệt kê database/collection: `show dbs`, `show collections`.
    

---

## **2. Insert (Create)**

- `db.users.insertOne({name: "A", age: 20})`
    
- `db.users.insertMany([{name: "B"}, {name: "C"}])`
    
- Lưu ý auto `_id`.
    

---

## **3. Find (Read)**

- **Cơ bản**:
    
    - `db.users.find({})` – lấy toàn bộ.
        
    - `db.users.find({name: "A"})`.
        
- **Toán tử so sánh**:
    
    - `$eq, $ne, $gt, $lt, $gte, $lte`.
        
    - `db.users.find({age: {$gt: 18}})`.
        
- **Toán tử logic**:
    
    - `$and, $or, $not, $nor`.
        
    - `db.users.find({$or: [{age: {$lt: 18}}, {age: {$gt: 30}}]})`.
        
- **Tập hợp**:
    
    - `$in, $nin`.
        
    - `db.users.find({name: {$in: ["A","B"]}})`.
        
- **Regex**:
    
    - `db.users.find({name: /th/})`.
        
- **Null / tồn tại**:
    
    - `db.users.find({phone: {$exists: true}})`.
        

---

## **4. Update**

- `updateOne(filter, {$set: {...}})`
    
- `updateMany(filter, {$set: {...}})`
    
- Toán tử update:
    
    - `$set`, `$unset`, `$inc`, `$mul`, `$rename`, `$currentDate`.
        
- Thay document mới: `replaceOne(filter, newDoc)`.
    

---

## **5. Delete**

- `deleteOne(filter)`
    
- `deleteMany(filter)`
    
- `db.users.remove({})` (cũ, ít dùng).
    

---

## **6. Projection (Chọn trường hiển thị)**

- `db.users.find({}, {name: 1, age: 1, _id: 0})`
    
- Chỉ lấy trường cần, bỏ `_id`.
    

---

## **7. Sort, Limit, Skip**

- `db.users.find().sort({age: 1})` – tăng dần.
    
- `db.users.find().sort({age: -1})` – giảm dần.
    
- `.limit(5)` – lấy 5 kết quả.
    
- `.skip(10)` – bỏ 10 kết quả đầu.
    

---

## **8. Query trong mảng**

- Tìm phần tử có trong mảng:
    
    - `db.users.find({tags: "vip"})`.
        
- `$all`: `db.users.find({tags: {$all: ["vip","new"]}})`.
    
- `$size`: `db.users.find({tags: {$size: 2}})`.
    
- `$elemMatch`: `db.users.find({scores: {$elemMatch: {math: {$gt: 8}, eng: {$gt: 7}}}})`.
    

---

## **9. Aggregate (Pipeline)**

- Cấu trúc: `db.orders.aggregate([{ stage1 }, { stage2 }, ...])`.
    
- `$match` – lọc.
    
- `$group` – nhóm + tính toán (`$sum, $avg, $min, $max`).
    
- `$sort` – sắp xếp.
    
- `$project` – chọn/trích trường mới.
    
- `$lookup` – join (giữa 2 collections).
    
- `$unwind` – tách mảng thành nhiều document.
    
- `$limit`, `$skip`, `$count`.
    

---

## **10. Index**

- Tạo: `db.users.createIndex({name: 1})`.
    
- Nhiều trường: `db.users.createIndex({name: 1, age: -1})`.
    
- Xem: `db.users.getIndexes()`.
    
- Xóa: `db.users.dropIndex("indexName")`.
    
- Hint query: `.hint({field: 1})`.
    

---

## **11. Bulk Operations**

- `db.users.bulkWrite([ { insertOne: { document: {...} } }, { updateOne: { filter: {...}, update: {...} } }, { deleteOne: { filter: {...} } } ])`.
    

---

## **12. Special Data Types**

- ObjectId (`_id`).
    
- ISODate.
    
- Embedded Document (document lồng document).
    
- Array.
    

---

## **13. Utility cú pháp thường dùng**

- Count: `db.users.countDocuments({age: {$gt: 20}})`.
    
- Distinct: `db.users.distinct("field")`.
    
- Rename Collection: `db.collection.renameCollection("newName")`.
    
- Drop Collection: `db.collection.drop()`.
    

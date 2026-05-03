# Non_SQL_Course
# MongoDB CRUD Operations Practice

## 📌 Overview

This project demonstrates basic **MongoDB operations** performed using the MongoDB shell (`mongosh`). It covers database creation, collection management, and various CRUD (Create, Read, Update, Delete) operations.

The purpose of this project is to understand how MongoDB works in a practical environment by executing real-time queries.

---

## 🛠️ Technologies Used

* MongoDB (v8.x)
* MongoDB Shell (mongosh)
* Windows Command Prompt

---

## 📂 Database Structure

### Database Name:

* `BCA1`

### Collections:

* `Students`
* `Employees`
* `Branch`

---

## 🚀 Operations Performed

### 1. Database & Collection Creation

```js
use BCA1
db.createCollection("Students")
db.createCollection("Employees")
db.createCollection("Branch")
```

---

### 2. Insert Operations

#### Insert One:

```js
db.students.insertOne({name:"Mike", age:19.4, cgpa:7.8, gender:"Male", fees:true})
```

#### Insert Many:

```js
db.students.insertMany([
  {name:"Virat", age:20, cgpa:8.9, gender:"Male", fees:false},
  {name:"Rakshita", age:19, cgpa:6.9, gender:"Female", fees:true}
])
```

---

### 3. Read Operations

#### Fetch All Records:

```js
db.students.find()
```

#### Filtering:

```js
db.students.find({age:20})
```

#### Projection:

```js
db.students.find({age:20}, {name:true, _id:false})
```

#### Sorting:

```js
db.students.find().sort({age:1, cgpa:1})
```

#### Limit:

```js
db.students.find().limit(2)
```

---

### 4. Update Operations

#### Update One:

```js
db.students.updateOne(
  {name:"Virat"},
  {$set:{age:23, cgpa:4.5}}
)
```

#### Update Many:

```js
db.students.updateMany(
  {},
  {$set:{courses:["CN","Web Tech","DAA"]}}
)
```

---

### 5. Delete Operations

#### Delete One:

```js
db.students.deleteOne({name:"Rakshita"})
```

#### Delete Many:

```js
db.students.deleteMany({fees:true})
```

---

### 6. Query Operators

#### Comparison Operators:

```js
db.students.find({age:{$gt:20}})
db.students.find({age:{$gte:20}})
db.students.find({age:{$lte:30}})
```

#### Logical Operators:

```js
db.students.find({$and:[{age:30},{cgpa:{$gte:8}}]})
db.students.find({$or:[{age:{$lte:28}},{cgpa:{$gte:9}}]})
```

#### In / Not In:

```js
db.students.find({age:{$in:[21,30]}})
db.students.find({age:{$nin:[21,30]}})
```

#### Not Equal:

```js
db.students.find({name:{$ne:"aru"}})
```

---

### 7. Indexing

#### Create Index:

```js
db.students.createIndex({name:1})
```

#### View Indexes:

```js
db.students.getIndexes()
```

#### Drop Indexes:

```js
db.students.dropIndexes()
```

---

## ⚠️ Common Errors Faced

* Case sensitivity issues (`"Virat"` vs `"virat"`)
* Syntax errors in queries
* Incorrect operators (e.g., `cgpa < 9.2` instead of `$lt`)
* Missing commas or brackets

---

## 📊 Key Learnings

* MongoDB is schema-less and flexible
* CRUD operations are simple and powerful
* Query operators provide advanced filtering
* Indexing improves query performance
* Case sensitivity matters in MongoDB

---

## 📎 Reference

All commands and outputs are based on actual terminal execution:


---

## ✨ Conclusion

This project provides a strong foundation for working with MongoDB. It demonstrates how to efficiently manage data using collections and perform complex queries with ease.

---

## 👩‍💻 Author

**Vanishree Ganagi**

---

# 🎓 Student Lookup System (Supabase + Firebase + Vercel)

A simple full-stack web application built using **Backend-as-a-Service (BaaS)** tools.
This project demonstrates how to use **Supabase** for database operations and **Firebase** for activity logging (audit system), all deployed via **Vercel**.

---

## 🚀 Project Overview

This application allows users to:

* 🔍 Search student details using Roll Number
* ➕ Add new student records
* ✏️ Update existing student details
* 📝 Track all activities (search, add, update) using Firebase

---

## 🛠️ Tech Stack

| Technology             | Purpose                         |
| ---------------------- | ------------------------------- |
| **HTML + JavaScript**  | Frontend UI and logic           |
| **Supabase**           | Database (students table)       |
| **Firebase Firestore** | Activity logging / audit system |
| **Vercel**             | Deployment                      |
| **GitHub**             | Version control                 |

---

## 🧩 Architecture

```
User تعامل (Browser)
        ↓
Frontend (HTML + JS)
        ↓
----------------------------
|        BaaS Layer        |
|--------------------------|
| Supabase  → Student Data |
| Firebase  → Activity Log |
----------------------------
```

---

## 📂 Features

### 1. 🔍 Search Student

* Enter Roll Number
* Fetches student data from Supabase
* Logs activity in Firebase

### 2. ➕ Add Student

* Add Roll Number, Name, Marks
* Stores data in Supabase
* Logs "created student" in Firebase

### 3. ✏️ Update Student

* Modify Name and Marks
* Updates record in Supabase
* Logs "updated student" in Firebase

### 4. 📝 Activity Logging

* Every action is recorded in Firebase Firestore:

  * checked details
  * created student
  * updated student

---

## 🗄️ Database Schema

### Supabase (students table)

| Column | Type                  |
| ------ | --------------------- |
| id     | Integer (Primary Key) |
| name   | Text                  |
| marks  | Integer               |

---

### Firebase Firestore (activities collection)

```json
{
  "roll": "101",
  "activity": "checked details",
  "time": "2026-04-19T12:30:00Z"
}
```

---

## ⚙️ Setup Instructions

### 1. Clone Repository

```bash
git clone https://github.com/your-username/student-lookup.git
cd student-lookup
```

---

### 2. Configure Supabase

* Go to Supabase project → Settings → API
* Copy:

  * Project URL
  * Anon Public Key

Update in code:

```js
const supabaseClient = window.supabase.createClient(
  "YOUR_SUPABASE_URL",
  "YOUR_SUPABASE_ANON_KEY"
);
```

---

### 3. Configure Firebase

* Go to Firebase Console → Project Settings
* Copy config object

Update in code:

```js
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "...",
  projectId: "...",
};
```

---

### 4. Run Locally

Just open `index.html` in your browser.

---

### 5. Deploy on Vercel

* Push code to GitHub
* Import repo in Vercel
* Deploy

---

## 🔍 How to View Logs (Audit)

1. Open Firebase Console
2. Go to **Firestore Database**
3. Open **activities collection**
4. View all user actions with timestamps

---

## 🔐 Security Notes

* Uses **Supabase Anon Key** (public)
* Recommended:

  * Enable Row Level Security (RLS)
  * Add policies for controlled access

---

## 🎯 Learning Outcomes

* Understanding of BaaS architecture
* Integration of multiple backend services
* CRUD operations using Supabase
* Real-time logging using Firebase
* Deployment using Vercel

---

## 🚀 Future Improvements

* 🗑️ Delete student feature
* 📊 Dashboard UI (table view)
* 🔐 Authentication system
* 📡 Real-time updates
* 📈 Analytics on activity logs

---

## 🙌 Conclusion

This project demonstrates how modern web apps can be built quickly using **Backend-as-a-Service platforms** without managing traditional servers.

---

## 👨‍💻 Author

**Gowtham Sai**

---

## ⭐ If you like this project

Give it a star on GitHub!

# 🚗 Vehicle Rental System

A **web-based application** that allows users to browse, verify licenses, and book vehicles for rent.
The system is developed using **Java Servlets**, **JDBC**, **HTML**, **CSS**, and **JavaScript**, with **MySQL** as the backend database.

---

## 🧩 Project Overview

The Vehicle Rental System is designed to simplify the process of renting vehicles online.
Users can view available vehicles, check license validity, and make bookings based on the number of days they wish to rent.
The system calculates the total cost automatically and keeps booking records linked to the user’s account.

---

## ⚙️ Technologies Used

| Layer        | Technology            |
| ------------ | --------------------- |
| **Frontend** | HTML, CSS, JavaScript |
| **Backend**  | Java (Servlets, JDBC) |
| **Database** | MySQL                 |
| **Server**   | Apache Tomcat         |
| **IDE**      | Eclipse / NetBeans    |

---

## 🧱 Project Modules

### 1️⃣ **User Module**

* User registration and login.
* Username stored for tracking bookings.
* Session handling for personalized user actions.

### 2️⃣ **Vehicle Module**

* Displays list of available vehicles with details like name, type, and price per day.
* Each vehicle has a “Book” button.

### 3️⃣ **License Verification Module**

* User enters their license number.
* System verifies the license validity.
* If valid → redirects to booking page.

### 4️⃣ **Booking Module**

* Vehicle details auto-filled.
* User enters **number of days**.
* System calculates **total cost = days × price per day**.
* Booking is saved with the username and vehicle details.

### 5️⃣ **Booking History Module**

* Displays previous bookings for logged-in users.
* Allows users to view their rental records.

---

## 🗄️ Database Design (MySQL)

### **Tables:**

#### 1. `users`

| Column   | Type         | Description   |
| -------- | ------------ | ------------- |
| username | VARCHAR(50)  | Primary key   |
| password | VARCHAR(50)  | User password |
| email    | VARCHAR(100) | User email    |

#### 2. `vehicles`

| Column        | Type         | Description          |
| ------------- | ------------ | -------------------- |
| vehicle_id    | INT          | Primary key          |
| name          | VARCHAR(100) | Vehicle name         |
| type          | VARCHAR(50)  | Car / Bike etc.      |
| price_per_day | DOUBLE       | Rental price per day |

#### 3. `licenses`

| Column     | Type        | Description     |
| ---------- | ----------- | --------------- |
| license_no | VARCHAR(50) | Primary key     |
| username   | VARCHAR(50) | Linked user     |
| status     | VARCHAR(20) | Valid / Invalid |

#### 4. `bookings`

| Column       | Type        | Description           |
| ------------ | ----------- | --------------------- |
| booking_id   | INT         | Primary key           |
| username     | VARCHAR(50) | User who booked       |
| vehicle_id   | INT         | Vehicle reference     |
| days         | INT         | Number of rental days |
| total_cost   | DOUBLE      | Computed total        |
| booking_date | DATE        | Date of booking       |

---

## 🚀 How It Works

1. **User Login/Register**

   * New users can sign up; existing users can log in.

2. **Browse Vehicles**

   * Displays available vehicles with details.

3. **License Verification**

   * User enters license number → verified from database.
   * If valid → redirects to booking page.

4. **Book Vehicle**

   * Vehicle details auto-filled.
   * User enters number of days → total cost is auto-calculated.
   * Booking details stored in database.

5. **View Booking History**

   * Users can view all their past rentals.

---

## 🧰 Setup Instructions

### Prerequisites:

* JDK 8 or above
* Apache Tomcat 9 or above
* MySQL Server
* Eclipse / NetBeans IDE

### Steps to Run:

1. **Clone Repository**

   ```bash
   git clone https://github.com/Bharanidharan-2402/Vehicle-Rental-System.git
   ```

2. **Database Setup**

   * Create a database named `vehicle_rental`.
   * Import the provided SQL file (`vehicle_rental.sql`).
   * Update database credentials in `DBConnection.java`:

     ```java
     String url = "jdbc:mysql://localhost:3306/vehicle_rental";
     String user = "root";
     String pass = "your_password";
     ```

3. **Deploy to Tomcat**

   * Place the project inside the Tomcat `webapps` folder or deploy via your IDE.

4. **Run the Project**

   * Start Tomcat server.
   * Open browser → `http://localhost:8080/vehicle_rental_system/`

---

## 📸 Key Features Snapshot

* ✅ User login and session handling
* ✅ Vehicle listing with dynamic data
* ✅ License verification before booking
* ✅ Auto-calculated total cost
* ✅ Booking history tracking

---

## 🧠 Learning Highlights

* CRUD operations using **JDBC**
* Request and session handling with **Servlets**
* Frontend-backend integration using **HTML forms and JSP pages**
* Dynamic database interaction using **MySQL**

---

## 🏁 Future Enhancements

* Add admin panel for managing vehicles and bookings.
* Implement online payment gateway.
* Add email notifications for bookings.
* Include vehicle image uploads.

---

## 👨‍💻 Author

**Bharanidharan Bharanidharan**
🎓 Engineering Student 
💡 Passionate about web development and full-stack technologies

---

## 🏷️ License

This project is developed for educational purposes under the MIT License.

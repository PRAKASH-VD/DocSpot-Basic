### 🩺 DocSpot – Doctor Appointment & Management System

A full-stack MERN application for managing doctors, appointments, users, and admin operations.

## 📌 Overview

DocSpot is a doctor appointment booking system built using the MERN Stack (MongoDB, Express, React, Node.js).
The application provides:

👨‍⚕️ Admin Panel – Add doctors, manage details, view appointments

👤 Patients – Book appointments, view doctor profiles

🔐 Authentication – Admin login & protected routes

🗂️ Doctor Management – Add/Delete/List doctors

🌐 REST API Backend

This README explains installation, environment setup, folder structure, and API usage.

### 🚀 Tech Stack
## Frontend

React JS

Tailwind CSS

Axios

React Router

React Toastify

Backend

Node.js

Express.js

Mongoose (MongoDB ODM)

JWT Authentication

Multer for Image Uploads

Bcrypt.js

Database

MongoDB Atlas / Local MongoDB

### 📁 Project Folder Structure
DocSpot/
│
├── backend/
│   ├── controllers/
│   ├── models/
│   ├── routes/
│   ├── middleware/
│   ├── uploads/
│   ├── server.js
│   ├── .env
│   └── package.json
│
└── frontend/
    ├── src/
    │   ├── components/
    │   ├── pages/
    │   ├── context/
    │   ├── assets/
    │   ├── App.jsx
    │   └── main.jsx
    ├── public/
    ├── package.json

### 🔧 Backend Installation
1. Navigate to backend folder:
cd backend

2. Install dependencies:
npm install

3. Create a .env file:
PORT=4000
MONGO_URL=your_mongodb_connection_string
JWT_SECRET=your_secret
CLOUDINARY_NAME=xxxx (if using cloud upload)
CLOUDINARY_API_KEY=xxxx
CLOUDINARY_API_SECRET=xxxx

4. Start server:
npm start


If successful:

Server is running on port 4000
Database connected

### 🎨 Frontend Installation
1. Navigate to frontend folder:
cd frontend

2. Install dependencies:
npm install

3. Start frontend:
npm run dev

### 🔐 Admin Login

Admin login uses JWT authentication.

## Sample Admin Credentials:

Email: admin@docspot.com
Password: Admin@123

## 📌 Add Doctor – API
POST /api/admin/add-doctor
Form-Data Required
Field	Type	Required	Description
image	File	Yes	Doctor image
name	String	Yes	Doctor full name
email	String	Yes	Unique doctor login email
password	String	Yes	Hashed before saving
experience	String	Yes	Example: "5 Year"
fees	Number	Yes	Consultation fees
about	String	Yes	Doctor description
speciality	String	Yes	e.g. Dermatologist
degree	String	Yes	MBBS / MD / etc
address	JSON string	Yes	{ "line1": "", "line2": "" }
Example Address Sent From Frontend:
formData.append("address", JSON.stringify({
  line1: address1,
  line2: address2
}));

## 🗂️ Sample Doctor JSON
{
  "name": "Dr. Rohan Sharma",
  "email": "rohan.sharma@example.com",
  "password": "Doctor@123",
  "experience": "5 Year",
  "fees": 500,
  "about": "Experienced general physician specializing in lifestyle diseases and preventive care.",
  "speciality": "General physician",
  "degree": "MBBS, MD (General Medicine)",
  "address": {
    "line1": "123, Green Park Road",
    "line2": "Bangalore, Karnataka 560001"
  },
  "image": "doctor-rohan.jpg"
}

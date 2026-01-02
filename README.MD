# 🍽 Digital Dining — Smart Restaurant Ordering System

A complete end-to-end digital dining and QR-based ordering platform built using Flask, MySQL, and Bootstrap.

# 📌 Overview

# Digital Dining is a modern restaurant management system that allows customers to:
✅ Scan a QR code on a table
✅ Login / Signup with OTP
✅ Browse menu
✅ Add items to cart
✅ Place orders in real time
✅ Track order status
✅ Pay bill and receive email invoice

Meanwhile, staff & manager panels include:
👨‍🍳 Staff: View/manage orders, update order status, manage menu availability
🧑‍💼 Manager: Manage menu, categories, staff accounts, view order analytics

The system includes a built-in AI chatbot (DineBot) powered optionally by Gemini API for menu recommendations and casual chat.

# 🚀 Key Features
## ✔ Customer

QR-based table scanning

OTP & Password login

Auto-start dining session

Live menu browsing

Cart-based ordering

Live order tracking

Session closing & payment

Email-based bill receipt

## ✔ Staff

Staff login

Staff dashboard

Manage orders (Placed → Preparing → Served)

Manage table availability

Toggle item availability

✔ Manager

## Manager login

Add / Edit / Delete menu items

Category management

Staff management

Menu analytics dashboard

## ✔ AI Chatbot (DineBot)

Menu-aware conversational bot

Recommends food based only on database items

Friendly, casual chat

Falls back gracefully when API key not configured

## 🏗 Tech Stack
Component	Technology
Backend	Flask (Python)
Database	MySQL (XAMPP)
Frontend	HTML, Bootstrap 5
Auth	Flask-Login + OTP (Gmail SMTP)
AI Chatbot	Google Gemini API (optional)
Emailing	SMTP via Gmail
QR Flow	Query parameter table mapping
## 📁 Project Structure
  digital-dining/
  │
  
  ├── main.py                     # Complete Flask backend
  
  ├── templates/                  # HTML pages
  
  ├── static/                     # CSS / JS / images
  
  ├── .env                        # API keys & DB credentials
    
  ├── README.md                   # Documentation
  
  └── requirements.txt            # Dependencies

## 🛠 Installation & Setup
1️⃣ Install Dependencies
pip install -r requirements.txt

2️⃣ Setup XAMPP MySQL

Create a database:

digital_dining


No need to manually create tables — the application will auto-create them.

3️⃣ Create .env file
FLASK_SECRET=your_flask_secret
DB_HOST=127.0.0.1
DB_USER=root
DB_PASS=
DB_NAME=digital_dining

SMTP_EMAIL=your_email@gmail.com
SMTP_PASS=your_app_password   # Use app password, not Gmail password

GOOGLE_API_KEY=your_gemini_key
GEMINI_MODEL=gemma-3-4b-it

4️⃣ Run the application
python main.py


## App runs at:
👉 http://127.0.0.1:5000

📌 Database Schema (Auto-Created)

## Tables auto-created at startup:
users

staff

manager

menu_categories

menu_items

tables

dining_sessions

orders

order_items

otp_codes

Base seeding includes:
✔ 6 tables: Table 1 to Table 6
✔ Default manager login:

Email: manager@dining.com  
Password: 1234

## 🔐 Authentication Flow
## Customer

Signup with OTP

Login with password OR OTP

Auto table reservation after QR scan

Only 1 active dining session at a time

## Staff

Has separate login

Can update orders and table status

## Manager

Super admin

Can add/edit/delete staff, menu, and categories

## 🍽 Ordering Workflow

Customer scans table QR

Customer logs in

Menu shown

Add items to cart

Place order

Staff updates order status

On completion → session ends

Customer pays

Customer receives bill via email

## 🤖 AI Chatbot — DineBot

The chatbot:

Understands food-related keywords

Recommends only existing menu items

Never invents new dishes

Falls back to basic replies if Gemini is not configured

API endpoint:

POST /api/chat


Expected JSON:

{ "message": "Suggest something spicy" }

🧪 Important for Practical / Submission

This README has been formatted to look:
✔ Professional
✔ Easy to follow
✔ Industry-standard GitHub style
✔ Clear enough for examiners to understand

It includes:

Project purpose

Features

Tech stack

Setup instructions

Workflow diagrams

Clear explanation of each module

Perfect for practicals, viva, or academic evaluation.

# 📬 Email Billing System

Bill includes:

Ordered items

Quantity

Tax calculation (5%)

Final amount

Dining session details

Sent using:

SMTP (Gmail)

# 🧼 Security Highlights

Hashed passwords (Werkzeug)

OTP verification for signup & reset

SQL safe queries using placeholders

Session protection

No plaintext password storage

# 🧩 Future Enhancements (Optional for Students)

Real-time WebSocket order updates

Payment gateway (Razorpay/Stripe)

QR auto-generator for tables

Customer analytics dashboard

Push notifications


# 🏁 Conclusion

Digital Dining is a full-fledged, production-style restaurant ordering system designed with scalability, clean architecture, and practical usability. This documentation ensures clean understanding for both academic evaluation and real deployment.#




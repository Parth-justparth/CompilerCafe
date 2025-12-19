🍽️ Digital Dining — Smart Restaurant Ordering SystemDigital Dining is an end-to-end QR-based ordering platform designed to modernize the restaurant experience. From table-side scanning to AI-powered menu recommendations, it bridges the gap between customers, kitchen staff, and management.📌 Project OverviewDigital Dining replaces traditional paper menus with a dynamic digital interface. Customers scan a table-specific QR code to initiate a session, while staff manage the workflow in real-time.🌟 Key FeaturesCustomer App: OTP-based authentication, live menu browsing, cart management, and real-time order tracking.Staff Panel: Real-time order status updates (Placed → Preparing → Served) and table availability management.Manager Dashboard: Full CRUD operations for menu/staff, category management, and sales analytics.DineBot AI: A Gemini-powered chatbot that provides intelligent food recommendations based strictly on the current database menu.Automated Billing: Instant email invoices sent via SMTP upon session completion.🏗️ Tech StackComponentTechnologyBackendFlask (Python)DatabaseMySQL (via XAMPP)FrontendHTML5, CSS3, Bootstrap 5AuthenticationFlask-Login + OTP (Gmail SMTP)AI EngineGoogle Gemini API (Gemma-3-4b-it)EmailingSMTP via Gmail📁 Project StructurePlaintextdigital-dining/
├── main.py              # Central Flask application logic & DB Models
├── templates/           # Jinja2 HTML templates (Auth, Menu, Admin, Staff)
├── static/              # CSS, JavaScript, and Brand Images
├── .env                 # Secret keys and API credentials
├── requirements.txt     # Python dependencies
└── README.md            # Documentation
🛠️ Installation & Setup1. Clone the RepositoryBashgit clone https://github.com/your-username/digital-dining.git
cd digital-dining
2. Install DependenciesBashpip install -r requirements.txt
3. Database Configuration (XAMPP)Open XAMPP Control Panel and start Apache and MySQL.Go to phpMyAdmin and create a database named digital_dining.Note: The application uses SQLAlchemy; tables will be auto-created and seeded with default data (Table 1-6) on the first run.4. Environment SetupCreate a .env file in the root directory:Code snippetFLASK_SECRET=your_secret_key
DB_HOST=127.0.0.1
DB_USER=root
DB_PASS=
DB_NAME=digital_dining
SMTP_EMAIL=your_email@gmail.com
SMTP_PASS=your_gmail_app_password
GOOGLE_API_KEY=your_gemini_api_key
5. Run the AppBashpython main.py
Visit http://127.0.0.1:5000 in your browser.🔄 System WorkflowEntry: Customer scans QR code $\rightarrow$ Table ID is captured via URL parameters.Session: Customer logs in (OTP) $\rightarrow$ Active session is created for that table.Ordering: Items added to cart $\rightarrow$ Order sent to Staff Dashboard.Processing: Staff marks order as "Preparing" then "Served".Checkout: Customer ends session $\rightarrow$ System calculates total + 5% tax $\rightarrow$ Bill emailed to customer.🤖 DineBot (AI Assistant)DineBot is more than just a chatbot; it is context-aware.It fetches the current menu from the MySQL database.It uses the Gemini API to understand user intent (e.g., "Suggest something spicy").It filters recommendations to ensure it only suggests items currently available in the kitchen.🛡️ Security MeasuresPassword Hashing: Uses Werkzeug for secure credential storage.OTP Verification: Ensures valid email addresses for all customers.SQL Injection Prevention: Uses SQLAlchemy ORM for parameterized queries.Protected Routes: Unauthorized users cannot access Staff or Manager dashboards.👨‍💻 ContributorsParth SinghPranshu Singla🏁 ConclusionDigital Dining is a production-ready architectural model for modern eateries. It streamlines operations, reduces human error in order taking, and provides a premium experience for diners through AI and automation.

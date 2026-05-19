# Kashmir Suraksha - Emergency Response System

## 🌟 What is this project?
Kashmir Suraksha is a web-based emergency response application designed specifically for the 10 districts of Kashmir. Its primary motto is **"One Tap Can Save a Life"**. 

Citizens can use this application to instantly send SOS alerts for Police, Medical, Fire, or Disaster emergencies. The app captures the user's details and exact GPS location, forwarding them directly to the respective department's admin dashboard for immediate rescue action.

---

## 💻 Technologies Used & Their Purpose
This project is built as a pure frontend application, meaning it runs seamlessly directly in the web browser without needing a complex backend server.

* **HTML5**: Used for creating the core structure of the application, including the SOS buttons, emergency forms, and the admin dashboards.
* **CSS3**: Used for styling the application, making it fully responsive (works perfectly on both mobile phones and desktop computers), and adding life-saving visual animations (like the red pulsating SOS button).
* **JavaScript (ES6+)**: The "brain" of the application. It handles all the interactive logic, such as simulating OTP verification, validating phone numbers, rate-limiting (preventing spam), and managing the user session.
* **LocalStorage API**: Acts as our local database. All emergency requests, user data, and admin sessions are securely stored in the browser's local storage.
* **Geolocation API**: Used to automatically detect the exact GPS coordinates (latitude and longitude) of the person in distress so the rescue team knows exactly where to go.

---

## 🔗 How Components Connect to Each Other
The application is designed with two main interconnected parts:

1. **User Application (`INDEX.HTML`)**: This is the citizen-facing side. When a user submits an SOS request, the JavaScript captures all the form data (name, phone number, GPS location, district, and emergency type) and saves it directly to the browser's `LocalStorage`.
2. **Admin Panel (`ADMIN.HTML`)**: This is the control center for the authorities. It continuously reads from the `LocalStorage`. When a new emergency is logged by the User Application, the Admin Panel instantly fetches this data and displays it on the dashboard so the dispatch team can take action.

Because both pages share the same `LocalStorage`, they communicate with each other in real-time without needing an external database.

---

## 👑 Admin Roles & Responsibilities

The system is highly secure and uses Role-Based Access Control (RBAC). It is divided into 5 distinct administrative roles to ensure that emergencies are handled by the correct department:

### 1. The Grand Admin (Super Admin)
* **Who should this be?** A top-level government official, the Chief of Police, or the primary System Administrator who oversees the entire emergency response grid for Kashmir.
* **What they do:** They have unrestricted master access to **ALL** departments. From their dashboard, they can monitor Police, Medical, Fire, and Disaster emergencies all at once and switch between department views.
* **Credentials:** `grandadmin` / `grandadmin123`

### 2. Department Admins (The Sub-Admins)
These admins only have access to their specific department's emergencies. They cannot see alerts meant for other departments, ensuring data privacy and focused response. 

* **Police Admin**: Dedicated to the local police force. Handles law & order, crime, theft, and security emergencies.
  * *Credentials:* `policeadmin` / `police123`
* **Medical Admin**: Dedicated to hospitals and ambulance dispatchers. Handles health emergencies, accidents, and injuries.
  * *Credentials:* `medicaladmin` / `medical123`
* **Fire Admin**: Dedicated to the Fire and Emergency Services. Handles fire incidents and explosions.
  * *Credentials:* `fireadmin` / `fire123`
* **Disaster Management Admin**: Dedicated to the State Disaster Response Force (SDRF). Handles natural disasters like floods, earthquakes, and landslides.
  * *Credentials:* `disasteradmin` / `disaster123`

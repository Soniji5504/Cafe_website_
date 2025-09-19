# Pizza Vincent — Cafe Website

[![PHP](https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white)](https://www.php.net) 
[![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com) 
[![XAMPP](https://img.shields.io/badge/XAMPP-A8D0E6?style=for-the-badge)](https://www.apachefriends.org/index.html) 
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5) 
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS) 
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

---

## Repository
`https://github.com/Soniji5504/Cafe_website_` — a ready-to-run PHP + MySQL restaurant website with user-facing pages (menu, order, reservation) and a simple admin area to manage orders/reservations. The repo contains SQL dump (`restaurant_website.sql`) you can import to create the database schema and sample data.

---

## Table of contents
- [Overview](#overview)  
- [Features](#features)  
- [Tech stack](#tech-stack)  
- [Project structure](#project-structure)  
- [Requirements](#requirements)  
- [Quick install (XAMPP local)](#quick-install-xampp-local)  
- [Database import (MySQL)](#database-import-mysql)  
- [Database connection (`connect.php`) example](#database-connection-connectphp-example)  
- [Admin area](#admin-area)  
- [How it works (user flow)](#how-it-works-user-flow)  
- [Customizing the site](#customizing-the-site)  
- [Troubleshooting & common fixes](#troubleshooting--common-fixes)  
- [Security best practices](#security-best-practices)  
- [Deployment notes](#deployment-notes)  
- [Contributing](#contributing)  
- [License](#license)  
- [Contact](#contact)

---

## Overview
**Pizza Vincent** is a simple restaurant/cafe website built with vanilla PHP, MySQL, HTML, CSS and JavaScript. It provides:
- a public menu and order page,  
- an online ordering flow (stores orders in DB),  
- a table reservation page (stores reservations), and  
- an admin section to view/manage orders & reservations.

This project is ideal for running locally with XAMPP/WAMP/LAMP or deploying to any PHP-compatible shared host.

---

## Features
- Browse menu items and see item details.  
- Place food orders via `order_food.php`.  
- Make table reservations via `table-reservation.php`.  
- Admin dashboard under `admin/` to view/manage orders and reservations.  
- SQL dump included (`restaurant_website.sql`) to create schema and seed sample data.  
- Simple structure — easy to customize for learning or small restaurant MVPs.

---

## Tech stack
- PHP (server-side rendering)  
- MySQL / MariaDB (relational database)  
- HTML, CSS, JavaScript (frontend)  
- XAMPP/WAMP/LAMP for local development

---

## Project structure
Cafe_website_/
├── admin/ # Admin pages (orders/reservations management)
├── assets/ # images, css, js (static assets)
├── css/
├── js/
├── index.php # Homepage
├── menu.php # Menu listing (if present)
├── order_food.php # Order page & submission handler
├── table-reservation.php # Reservation page & submission handler
├── connect.php # Database connection (edit DB credentials here)
├── restaurant_website.sql # SQL dump (schema + sample data)
├── README.md
└── .gitignore

yaml
Copy code

---

## Requirements
- PHP 7.4+ (recommended)  
- MySQL 5.7+ or MariaDB  
- Apache (XAMPP recommended for local dev)  
- Browser (Chrome / Firefox)  

---

## Quick install (XAMPP local)

1. Download & install **XAMPP**: https://www.apachefriends.org.  
2. Start **Apache** and **MySQL** from the XAMPP control panel.  
3. Copy the project folder into XAMPP web root:  
   - Windows: `C:\xampp\htdocs\Pizza_Vincent\` (or any folder name you prefer)  
4. Import the SQL file (see next section).  
5. Update database credentials in `connect.php` (example below).  
6. Open the site in your browser:  
http://localhost/Pizza_Vincent/ # or folder name you used

pgsql
Copy code

---

## Database import (MySQL)

1. Open phpMyAdmin: `http://localhost/phpmyadmin`.  
2. Create a new database (example name: `pizza_vincent_db`).  
3. Select the new database, then go to **Import → Choose file** and upload `restaurant_website.sql`.  
4. Click **Go** — this will create tables and insert sample data (if included).

Alternatively from command line:
```bash
# replace values accordingly
mysql -u root -p
CREATE DATABASE pizza_vincent_db;
exit

# import SQL file
mysql -u root -p pizza_vincent_db < path/to/restaurant_website.sql
Database connection (connect.php) example
php
Copy code
<?php
// connect.php - example for local XAMPP (edit values as needed)
$host = 'localhost';
$user = 'root';
$pass = '';            // XAMPP default is empty password for root
$db_name = 'pizza_vincent_db';

$conn = mysqli_connect($host, $user, $pass, $db_name);

if (!$conn) {
    die("Connection failed: " . mysqli_connect_error());
}
?>
Admin area
The admin/ folder contains admin pages to view/manage orders/reservations.

If default admin credentials exist in the SQL dump, open restaurant_website.sql and search for inserts into the admins or users table to find username/password.

If no admin user is seeded, create one via phpMyAdmin in the relevant table.

For security, change default admin credentials after first login.

How it works (user flow)
User visits homepage and views the menu.

Order: user fills the order form on order_food.php → form POSTs to server → server inserts order row into orders table → order appears in admin panel.

Reservation: user fills table-reservation.php → reservation saved in DB → admin panel lists reservations for staff.

Admin logs into admin/ and can view, update or delete orders/reservations.

Customizing the site
Change menu items: edit tables like menu, items, or update static arrays used by menu pages.

Change text/logo: replace images in assets/images and update text in index.php or other templates.

Add new fields: update the SQL schema, then update PHP code that reads/writes those fields.

Styling: modify files in css/ or update Bootstrap classes (if Bootstrap is included).

Troubleshooting & common fixes
Blank page / white screen: enable PHP error display temporarily.

php
Copy code
ini_set('display_errors', 1);
ini_set('display_startup_errors', 1);
error_reporting(E_ALL);
DB connection error: verify connect.php credentials, ensure MySQL service is running.

Forms not submitting: check browser console for JS errors & server logs for PHP errors.

Admin login not working: verify credentials in DB or reset via phpMyAdmin.

Security best practices
Do not commit connect.php with real credentials to public repos.

Sanitize and validate all user inputs (SQL injection protection).

Use prepared statements (mysqli with bound params or PDO).

Store passwords with password_hash() & password_verify().

Validate uploaded files (size/type) and rename safely.

Deployment notes
Host on any PHP-supported hosting (cPanel, shared hosting, VPS, DigitalOcean).

Import the SQL file into production DB.

Update connect.php with production credentials.

Configure Apache .htaccess (optional) for clean URLs / security.

Contributing
Fork the repo.

Create a feature branch: git checkout -b feat/your-feature.

Commit changes with clear messages.

Push branch and open a Pull Request.

License
Choose and add a license (MIT recommended). Example:

This project is licensed under the MIT License — see the LICENSE file for details.

Contact
GitHub Repo: Cafe Website

Author: Your Name (replace with your details)

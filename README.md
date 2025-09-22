# 🍕 Pizza Vincent — Cafe Management System

[![PHP](https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white)](https://www.php.net) 
[![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com) 
[![XAMPP](https://img.shields.io/badge/XAMPP-A8D0E6?style=for-the-badge)](https://www.apachefriends.org/index.html) 
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5) 
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS) 
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

---

## 📍 Repository
`https://github.com/Soniji5504/Cafe_website_` — A ready-to-run PHP + MySQL restaurant website with user-facing pages (menu, order, reservation) and admin panel for complete restaurant management.

---

## 📋 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Requirements](#requirements)
- [Quick Install (XAMPP)](#quick-install-xampp)
- [Database Setup](#database-setup)
- [Admin Panel](#admin-panel)
- [User Flow](#user-flow)
- [Customization](#customization)
- [Troubleshooting](#troubleshooting)
- [Security](#security)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## 🎯 Overview
**Pizza Vincent** is a comprehensive restaurant/cafe management system built with vanilla PHP, MySQL, HTML, CSS and JavaScript. Perfect for small to medium restaurants looking for a complete digital solution.

## ✨ Features

### 🌐 **Customer Experience**
- 📱 **Responsive Menu Display** - Browse categorized items with images & prices
- 🛒 **Online Food Ordering** - Multi-step ordering process with cart functionality
- 🪑 **Table Reservation System** - Real-time availability checking & booking
- 🖼️ **Image Gallery** - Showcase restaurant ambiance and dishes
- 📞 **Contact Form** - Direct communication with management
- 📱 **Mobile-Friendly** - Optimized for all devices

### 🔧 **Admin Management**
- 📊 **Dashboard** - Complete overview of operations & statistics
- 🍕 **Menu Management** - Add, edit, delete items and categories
- 📦 **Order Processing** - Track orders from placement to delivery
- 📅 **Reservation Control** - Manage table bookings and availability
- 👥 **Client Database** - Customer information management
- 🖼️ **Gallery Control** - Upload and organize restaurant images
- ⚙️ **Website Settings** - Configure restaurant details
- 👤 **User Management** - Admin accounts and permissions

### 🚀 **Advanced Features**
- 📧 **Email Integration** - PHPMailer for notifications
- 🔒 **Secure Authentication** - Session-based admin login
- ⚡ **AJAX Operations** - Smooth user experience
- 🛡️ **Data Validation** - Client & server-side security
- 📊 **Analytics Ready** - Track orders and reservations

## 🛠️ Tech Stack

### Backend
- **PHP 7.4+**: Server-side scripting
- **MySQL**: Database management system
- **PDO**: Database abstraction layer for secure queries

### Frontend
- **HTML5**: Semantic markup
- **CSS3**: Modern styling with custom properties
- **JavaScript/jQuery**: Interactive functionality and AJAX
- **Bootstrap 4**: Responsive framework
- **Font Awesome**: Icon library

### Libraries & Dependencies
- **PHPMailer**: Email functionality
- **jQuery**: JavaScript library for DOM manipulation
- **Bootstrap**: CSS framework for responsive design

## 📂 Project Structure

```
Cafe_website_/
├── admin/                          # 🔧 Admin Panel
│   ├── ajax_files/                 # AJAX handlers
│   ├── Design/                     # Admin assets (CSS, JS, fonts)
│   ├── Includes/                   # Functions, libraries, templates
│   ├── Uploads/images/             # Uploaded menu images
│   └── *.php                       # Admin management pages
├── Design/                         # 🎨 Frontend Assets
│   ├── css/                        # Stylesheets
│   ├── js/                         # JavaScript files
│   ├── fonts/                      # Font files
│   └── images/                     # Static images
├── Includes/                       # 📚 Core Functions
│   ├── functions/                  # PHP utilities
│   ├── libraries/                  # PHPMailer & dependencies
│   └── templates/                  # Reusable templates
├── connect.php                     # 🔗 Database connection
├── index.php                       # 🏠 Homepage
├── order_food.php                  # 🛒 Food ordering system
├── table-reservation.php           # 🪑 Table booking system
└── restaurant_website.sql          # 🗃️ Database schema & sample data
```

## 🗃️ Database Schema

The system uses **8 main tables** for complete restaurant management:

| Table | Purpose |
|-------|---------|
| 👥 **`clients`** | Customer information & contact details |
| 🔐 **`users`** | Admin user accounts & authentication |
| 📂 **`menu_categories`** | Food categories (burgers, pizzas, drinks, etc.) |
| 🍕 **`menus`** | Menu items with details, pricing & images |
| 📦 **`placed_orders`** | Customer orders & delivery information |
| 🔗 **`in_order`** | Order items (junction table for order-menu relationship) |
| 🪑 **`reservations`** | Table bookings & guest information |
| 🏪 **`tables`** | Available tables & seating capacity |
| 🖼️ **`image_gallery`** | Restaurant gallery images |
| ⚙️ **`website_settings`** | Site configuration & restaurant details |

## 🚀 Quick Install (XAMPP)

### 📋 Requirements
- **PHP 7.4+** (recommended)
- **MySQL 5.7+** or MariaDB
- **Apache** (XAMPP recommended)
- **Modern Browser** (Chrome/Firefox)

### ⚡ Installation Steps

1. **📥 Download & Install XAMPP**
   ```bash
   # Download from: https://www.apachefriends.org/
   # Start Apache and MySQL services
   ```

2. **📁 Setup Project**
   ```bash
   # Copy project to XAMPP web root:
   C:\xampp\htdocs\Pizza_Vincent\
   ```

3. **🗃️ Database Setup**
   - Open phpMyAdmin: `http://localhost/phpmyadmin`
   - Create database: `restaurant_website`
   - Import: `restaurant_website.sql`

4. **🔧 Configuration**
   Update `connect.php` if needed:
   ```php
   <?php
   $dsn = 'mysql:host=localhost;dbname=restaurant_website';
   $user = 'root';
   $pass = '';  // XAMPP default
   ?>
   ```

5. **🌐 Access Your Site**
   - **Website**: `http://localhost/Pizza_Vincent/`
   - **Admin Panel**: `http://localhost/Pizza_Vincent/admin/`

## 🔐 Admin Panel

### 🚪 Default Login Credentials
- **Username**: `admin_user`
- **Password**: `123456789`

### 🛡️ Security Note
**⚠️ Change default credentials after first login for security!**

### 📊 Admin Features
- View all orders and reservations
- Manage menu items and categories
- Upload gallery images
- Configure website settings
- Manage customer database

## 🔄 User Flow

### 👥 **Customer Journey**
1. **🏠 Homepage** → Browse featured items and restaurant info
2. **🍕 Menu** → View categorized food items with prices
3. **🛒 Order** → Multi-step ordering process:
   - Select menu items
   - Enter customer details
   - Confirm order
4. **🪑 Reservation** → Book tables:
   - Check availability
   - Select date/time
   - Provide contact info
5. **📞 Contact** → Direct communication

### 👨‍💼 **Admin Workflow**
1. **🔐 Login** → Secure admin authentication
2. **📊 Dashboard** → Overview of operations
3. **🍕 Menu Management** → Add/edit items and categories
4. **📦 Order Processing** → Track and update order status
5. **📅 Reservation Management** → Handle table bookings
6. **🖼️ Gallery** → Upload and organize images
7. **⚙️ Settings** → Configure restaurant details

## 🎨 Customization

### 🍕 **Menu Customization**
- **Add Categories**: Create new food categories (appetizers, mains, desserts)
- **Menu Items**: Update items, prices, descriptions, and images
- **Pricing**: Dynamic pricing system with easy updates

### 🎨 **Visual Customization**
- **Logo**: Replace in `Design/images/restaurant-logo.png`
- **Colors**: Modify CSS variables in `Design/css/main.css`
- **Images**: Update gallery and background images
- **Text**: Edit content in PHP files

### ⚙️ **Functionality**
- **Payment Integration**: Add payment gateways
- **Email Settings**: Configure SMTP in PHPMailer
- **Database**: Extend tables for additional features
- **Languages**: Add multi-language support

## 🔧 Troubleshooting

### 🚨 **Common Issues & Fixes**

#### **Blank Page / White Screen**
```php
// Add to top of PHP files for debugging
ini_set('display_errors', 1);
ini_set('display_startup_errors', 1);
error_reporting(E_ALL);
```

#### **Database Connection Error**
- ✅ Check XAMPP MySQL service is running
- ✅ Verify `connect.php` credentials
- ✅ Ensure database `restaurant_website` exists

#### **Forms Not Submitting**
- ✅ Check browser console for JS errors
- ✅ Verify PHP error logs
- ✅ Check file permissions

#### **Admin Login Issues**
- ✅ Default: `admin_user` / `123456789`
- ✅ Check users table in database
- ✅ Clear browser cache

#### **Image Upload Problems**
- ✅ Check `admin/Uploads/images/` permissions
- ✅ Verify PHP file size limits
- ✅ Ensure supported formats (JPG, PNG, GIF)

## 🛡️ Security

### 🔒 **Security Best Practices**
- **🚫 SQL Injection Protection**: PDO prepared statements
- **🧹 XSS Prevention**: Input sanitization and validation
- **🔐 Secure Sessions**: Admin authentication system
- **📁 File Upload Security**: Image validation and restrictions
- **🔑 Password Hashing**: Secure password storage

### ⚠️ **Important Security Notes**
- **Never commit `connect.php` with real credentials**
- **Use prepared statements for all database queries**
- **Validate and sanitize all user inputs**
- **Change default admin credentials immediately**
- **Keep PHP and MySQL updated**

## 🚀 Deployment

### 🌐 **Production Deployment**
1. **Choose Hosting**: Any PHP-compatible host (cPanel, shared hosting, VPS)
2. **Upload Files**: Transfer all project files to web root
3. **Database**: Import `restaurant_website.sql` to production database
4. **Configuration**: Update `connect.php` with production credentials
5. **Security**: Configure `.htaccess` for security and clean URLs

### 📊 **Performance Tips**
- **Image Optimization**: Compress images before upload
- **Caching**: Enable browser and server-side caching
- **Database**: Optimize queries and add indexes
- **CDN**: Use CDN for static assets in production

## 📈 Future Enhancements

- 💳 **Payment Gateway Integration** - Stripe, PayPal, Razorpay
- 🏢 **Multi-restaurant Support** - Franchise management
- 📱 **Mobile App** - Native iOS/Android applications
- 📊 **Analytics Dashboard** - Advanced reporting
- 📦 **Inventory Management** - Stock tracking
- 👥 **Staff Management** - Employee scheduling
- ⭐ **Customer Reviews** - Rating system
- 🎁 **Loyalty Program** - Customer rewards

## 🤝 Contributing

1. **🍴 Fork** the repository
2. **🌿 Create** feature branch: `git checkout -b feat/your-feature`
3. **💾 Commit** changes with clear messages
4. **🚀 Push** branch and open a Pull Request



## 📞 Contact

- **🐙 GitHub**: [Soniji5504](https://github.com/Soniji5504)
- **📧 Email**: [Contact Me](mailto:your-email@example.com)
- **🌐 Repository**: [Cafe Website](https://github.com/Soniji5504/Cafe_website_)

## 🙏 Acknowledgments

- **Bootstrap Team** - Responsive framework
- **PHPMailer Contributors** - Email functionality  
- **Font Awesome** - Icon library
- **jQuery Team** - JavaScript library
- **Open Source Community** - Inspiration and support

---

<div align="center">

**🍕 Built with ❤️ for Pizza Vincent Restaurant**

*Making restaurant management deliciously simple!*

</div>

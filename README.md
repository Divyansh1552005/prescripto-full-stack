# 🏥 Prescriptio - Complete Hospital Management System

A full-stack web application for managing hospital appointments, doctors, and patients with separate portals for users, doctors, and administrators.

![React](https://img.shields.io/badge/React-18.3.1-blue.svg)
![Node.js](https://img.shields.io/badge/Node.js-Express-green.svg)
![MongoDB](https://img.shields.io/badge/Database-MongoDB-brightgreen.svg)
![TailwindCSS](https://img.shields.io/badge/Styling-TailwindCSS-06B6D4.svg)

## 📋 Table of Contents

- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Installation](#-installation)
- [Environment Variables](#-environment-variables)
- [Usage](#-usage)
- [API Endpoints](#-api-endpoints)
- [Payment Integration](#-payment-integration)
- [Screenshots](#-screenshots)
- [Contributing](#-contributing)
- [License](#-license)

## ✨ Features

### 👨‍⚕️ **For Patients (Frontend)**
- **User Registration & Authentication** - Secure login/signup with JWT
- **Doctor Search & Filter** - Browse doctors by speciality
- **Appointment Booking** - Real-time slot booking system
- **Profile Management** - Update personal information and upload profile pictures
- **Payment Integration** - Pay online via Razorpay or Stripe
- **Appointment History** - View, cancel, and track appointments
- **Responsive Design** - Mobile-friendly interface

### 🩺 **For Doctors (Admin Panel)**
- **Doctor Dashboard** - View earnings, appointments, and patient statistics
- **Appointment Management** - Accept, complete, or cancel appointments
- **Profile Management** - Update availability, fees, and personal information
- **Patient Information** - Access patient details and medical history
- **Schedule Management** - Manage working hours and availability

### 👩‍💼 **For Administrators (Admin Panel)**
- **Admin Dashboard** - Overview of system statistics
- **Doctor Management** - Add, remove, and manage doctors
- **Appointment Oversight** - Monitor all appointments across the system
- **User Management** - View and manage patient accounts
- **System Analytics** - Track revenue, appointments, and user engagement

## 🛠 Tech Stack

### **Frontend (User Portal)**
- **React 18.3.1** - Modern React with hooks
- **Vite** - Fast build tool and development server
- **Tailwind CSS** - Utility-first CSS framework
- **React Router DOM** - Client-side routing
- **Axios** - HTTP client for API calls
- **React Toastify** - Elegant notifications

### **Admin Panel**
- **React 18.3.1** - Separate admin interface
- **Vite** - Build tool
- **Tailwind CSS** - Consistent styling
- **Context API** - State management for admin and doctor contexts

### **Backend (API Server)**
- **Node.js** - JavaScript runtime
- **Express.js** - Web application framework
- **MongoDB** - NoSQL database
- **Mongoose** - MongoDB object modeling
- **JWT** - Authentication tokens
- **Bcrypt** - Password hashing
- **Cloudinary** - Image storage and management
- **Multer** - File upload handling

### **Payment Gateways**
- **Razorpay** - Indian payment gateway
- **Stripe** - International payment processing

## 📁 Project Structure

```
prescripto-full-stack/
├── frontend/                 # Patient portal (React app)
│   ├── src/
│   │   ├── components/      # Reusable UI components
│   │   ├── pages/          # Page components
│   │   ├── context/        # Context providers
│   │   └── assets/         # Images and static files
│   ├── public/
│   └── package.json
│
├── admin/                   # Admin & Doctor portal (React app)
│   ├── src/
│   │   ├── components/     # Admin UI components
│   │   ├── pages/
│   │   │   ├── Admin/      # Admin-specific pages
│   │   │   └── Doctor/     # Doctor-specific pages
│   │   ├── context/        # Admin & Doctor contexts
│   │   └── assets/
│   └── package.json
│
├── backend/                # Node.js API server
│   ├── controllers/        # Route handlers
│   ├── models/            # MongoDB schemas
│   ├── routes/            # API routes
│   ├── middleware/        # Authentication & validation
│   ├── config/           # Database & service configs
│   └── server.js         # Entry point
│
└── README.md
```

## 🚀 Installation

### Prerequisites
- **Node.js** (v16 or higher)
- **MongoDB** (local or MongoDB Atlas)
- **Cloudinary Account** (for image uploads)
- **Razorpay Account** (for payments)
- **Stripe Account** (for payments)

### 1. Clone the Repository
```bash
git clone https://github.com/Divyansh1552005/prescripto-full-stack.git
cd prescripto-full-stack
```

### 2. Backend Setup
```bash
cd backend
npm install
```

### 3. Frontend Setup
```bash
cd ../frontend
npm install
```

### 4. Admin Panel Setup
```bash
cd ../admin
npm install
```

## 🔧 Environment Variables

Create a `.env` file in the `backend` directory:

```env
# Application Settings
CURRENCY="INR"
JWT_SECRET="your_jwt_secret_here"

# Admin Credentials
ADMIN_EMAIL="your_admin_email@example.com"
ADMIN_PASSWORD="your_secure_admin_password"

# Database
MONGODB_URI="your_mongodb_connection_string"

# Cloudinary (Image Storage)
CLOUDINARY_NAME="your_cloudinary_name"
CLOUDINARY_API_KEY="your_cloudinary_api_key"
CLOUDINARY_SECRET_KEY="your_cloudinary_secret_key"

# Payment Gateways
RAZORPAY_KEY_ID="your_razorpay_key_id"
RAZORPAY_KEY_SECRET="your_razorpay_key_secret"
STRIPE_SECRET_KEY="your_stripe_secret_key"
```

### Frontend Environment Variables
Create `.env` files in both `frontend` and `admin` directories:

```env
VITE_BACKEND_URL="http://localhost:4000"
VITE_RAZORPAY_KEY_ID="your_razorpay_key_id"
```

## 🎯 Usage

### Development Mode

1. **Start Backend Server**
```bash
cd backend
npm run server
# Server runs on http://localhost:4000
```

2. **Start Frontend (Patient Portal)**
```bash
cd frontend
npm run dev
# Runs on http://localhost:5173
```

3. **Start Admin Panel**
```bash
cd admin
npm run dev
# Runs on http://localhost:5174
```

### Production Mode

1. **Build Frontend**
```bash
cd frontend
npm run build
```

2. **Build Admin Panel**
```bash
cd admin
npm run build
```

3. **Start Production Server**
```bash
cd backend
npm start
```

## 🔗 API Endpoints

### **User Routes** `/api/user`
- `POST /register` - User registration
- `POST /login` - User login
- `GET /get-profile` - Get user profile
- `POST /update-profile` - Update user profile
- `POST /book-appointment` - Book appointment
- `GET /appointments` - Get user appointments
- `POST /cancel-appointment` - Cancel appointment
- `POST /payment-razorpay` - Razorpay payment
- `POST /payment-stripe` - Stripe payment

### **Doctor Routes** `/api/doctor`
- `POST /login` - Doctor login
- `GET /appointments` - Get doctor appointments
- `POST /cancel-appointment` - Cancel appointment
- `POST /complete-appointment` - Mark appointment complete
- `GET /dashboard` - Doctor dashboard data
- `GET /profile` - Doctor profile
- `POST /update-profile` - Update doctor profile

### **Admin Routes** `/api/admin`
- `POST /login` - Admin login
- `POST /add-doctor` - Add new doctor
- `GET /appointments` - Get all appointments
- `GET /all-doctors` - Get all doctors
- `POST /change-availability` - Change doctor availability

## 💳 Payment Integration

### Razorpay Setup
1. Create account at [Razorpay](https://razorpay.com/)
2. Get API keys from dashboard
3. Add keys to environment variables
4. Test with Razorpay test cards

### Stripe Setup
1. Create account at [Stripe](https://stripe.com/)
2. Get publishable and secret keys
3. Configure webhook endpoints
4. Test with Stripe test cards

## 🏥 Key Features Explained

### **Smart Appointment Booking**
- Real-time slot availability
- 30-minute time slots from 10 AM to 9 PM
- Automatic slot blocking after booking
- Date-wise slot management

### **Multi-Role Authentication**
- JWT-based authentication
- Role-based access control (Admin, Doctor, Patient)
- Secure password hashing with bcrypt
- Protected routes and middleware

### **Image Management**
- Cloudinary integration for profile pictures
- Automatic image optimization
- Secure file upload with Multer
- Image URL generation and storage

### **Payment Processing**
- Dual payment gateway support
- Secure payment verification
- Order tracking and receipts
- Failed payment handling

## 🔒 Security Features

- **Environment Variables** - All sensitive data in environment files
- **Password Hashing** - Bcrypt for secure password storage
- **JWT Authentication** - Stateless authentication tokens
- **Input Validation** - Validator.js for email and data validation
- **File Upload Security** - Multer with file type restrictions
- **CORS Configuration** - Cross-origin request handling

## 📱 Responsive Design

- **Mobile-First Approach** - Designed for mobile devices
- **Tailwind CSS** - Utility-first responsive design
- **Flexible Layouts** - Grid and flexbox layouts
- **Touch-Friendly** - Large buttons and touch targets
- **Cross-Browser** - Compatible with all modern browsers

## 🎨 UI/UX Features

- **Clean Interface** - Modern and intuitive design
- **Toast Notifications** - Real-time feedback for user actions
- **Loading States** - Visual feedback during API calls
- **Error Handling** - Graceful error messages and recovery
- **Consistent Styling** - Unified design system across portals

## 🚀 Deployment

### **Backend (Node.js)**
- Deploy to Heroku, Railway, or DigitalOcean
- Set environment variables in deployment platform
- Configure MongoDB Atlas for production database

### **Frontend & Admin (React)**
- Deploy to Vercel, Netlify, or similar
- Configure build settings for Vite
- Set up custom domains if needed

### **Database (MongoDB)**
- Use MongoDB Atlas for cloud database
- Configure proper indexes for performance
- Set up backup and monitoring

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Developer

**Divyansh Sharma**
- GitHub: [@Divyansh1552005](https://github.com/Divyansh1552005)
- Email: officialdslc1552005@gmail.com

## 🙏 Acknowledgments

- Thanks to all open-source libraries and their maintainers
- Special thanks to the React and Node.js communities
- Icons and images from various open-source resources

---

**⭐ If you find this project helpful, please give it a star on GitHub!**

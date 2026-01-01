# 🏥 MERN Hospital Management System - Setup Guide

## ✅ What's Been Done
- ✅ Installed all dependencies for Backend, Frontend, and Dashboard
- ✅ Created `config.env` file in the backend folder with environment variables

## 📋 Next Steps

### 1. **Configure Environment Variables**

Edit the `backend/config.env` file with your actual credentials:

```env
# MongoDB - Required!
MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/

# JWT Secret - Change this to a secure random string
JWT_SECRET_KEY=your_secure_random_key_here

# Cloudinary (for image uploads) - Get from https://cloudinary.com/
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
```

### 2. **Set Up MongoDB**

**Option A: Local MongoDB**
- Install MongoDB from https://www.mongodb.com/try/download/community
- Start MongoDB service: `brew services start mongodb-community` (macOS)
- Use: `mongodb://localhost:27017/MERN_STACK_HOSPITAL_MANAGEMENT_SYSTEM_DEPLOYED`

**Option B: MongoDB Atlas (Recommended)**
- Create account at https://www.mongodb.com/cloud/atlas
- Create a free cluster
- Get connection string and add to `config.env`

### 3. **Set Up Cloudinary (Optional but Recommended)**
- Sign up at https://cloudinary.com/
- Get your API credentials from the dashboard
- Add them to `config.env`

---

## 🚀 Running the Project

### **Terminal 1: Start Backend Server**
```bash
cd backend
npm run dev
```
- Server runs on: `http://localhost:4000`
- Uses nodemon for hot reload

### **Terminal 2: Start Frontend**
```bash
cd frontend
npm run dev
```
- Runs on: `http://localhost:5173`

### **Terminal 3: Start Dashboard (Admin Panel)**
```bash
cd dashboard
npm run dev
```
- Runs on: `http://localhost:5174`

---

## 📚 Project Structure

```
├── backend/          - Node.js/Express server
│   ├── controller/   - Business logic
│   ├── models/       - MongoDB schemas
│   ├── router/       - API routes
│   ├── middlewares/  - Auth, error handling
│   └── config.env    - Environment variables
│
├── frontend/         - Patient portal (React + Vite)
│   └── src/components/
│
└── dashboard/        - Admin panel (React + Vite)
    └── src/components/
```

---

## 🔐 Important Security Notes

1. **Change JWT_SECRET_KEY** - Use a strong random string in production
2. **Never commit `.env` files** - Keep credentials private
3. **Update CORS URLs** - Change frontend URLs in production
4. **MongoDB Password** - Use strong passwords, never hardcode them

---

## ⚠️ Troubleshooting

**Backend won't connect to MongoDB?**
- Verify MongoDB is running
- Check `MONGO_URI` in `config.env`
- Ensure MongoDB credentials are correct

**CORS errors?**
- Check `FRONTEND_URL_ONE` and `FRONTEND_URL_TWO` in `config.env`
- Ensure they match your running frontend/dashboard ports

**Image uploads not working?**
- Configure Cloudinary credentials
- Or remove file upload features if not needed

---

## 📦 Available Scripts

**Backend:**
- `npm start` - Run server (production)
- `npm run dev` - Run with nodemon (development)

**Frontend & Dashboard:**
- `npm run dev` - Start dev server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run lint` - Check code quality

---

## ✨ Ready to Go!
Your MERN stack project is now set up. Start the three servers in separate terminals and open the URLs above in your browser.

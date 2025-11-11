# ✅ EduMate Deployment Checklist

Use this checklist to ensure you complete all deployment steps.

## 📋 Pre-Deployment

- [ ] GitHub account created
- [ ] Render account created (https://render.com)
- [ ] Vercel account created (https://vercel.com)
- [ ] Railway account created (https://railway.app)
- [ ] MongoDB Atlas account created (https://mongodb.com/cloud/atlas)

## 🗄️ Database Setup

### MongoDB Atlas
- [ ] Created free cluster
- [ ] Created database user (username & password saved)
- [ ] Configured network access (0.0.0.0/0)
- [ ] Copied connection string
- [ ] Replaced `<password>` in connection string
- [ ] Tested connection (optional)

**MongoDB Connection String**:
```
mongodb+srv://edumate_user:YOUR_PASSWORD@cluster.mongodb.net/edumate_mongo?retryWrites=true&w=majority
```

### Railway MySQL
- [ ] Created new project
- [ ] Provisioned MySQL database
- [ ] Copied host, port, database, username, password
- [ ] Created JDBC connection string

**MySQL Connection String**:
```
jdbc:mysql://HOST:PORT/railway?useSSL=false&serverTimezone=UTC
```

## 📦 GitHub Repository

- [ ] Initialized git in project directory
- [ ] Created GitHub repository
- [ ] Pushed code to GitHub
- [ ] Verified all files are uploaded

**Commands used**:
```powershell
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/USERNAME/EduMate.git
git push -u origin main
```

## 🚀 Backend Deployment (Render)

- [ ] Created new Web Service on Render
- [ ] Connected GitHub repository
- [ ] Configured build settings:
  - Root Directory: `Backend`
  - Build Command: `mvn clean package -DskipTests`
  - Start Command: `java -Dspring.profiles.active=prod -jar target/backend-0.0.1-SNAPSHOT.jar`
- [ ] Added environment variables (see below)
- [ ] Deployment successful
- [ ] Copied backend URL: `_____________________`

### Backend Environment Variables
```
PORT=8080
SPRING_PROFILES_ACTIVE=prod
DATABASE_URL=<your-mysql-connection-string>
DB_USERNAME=root
DB_PASSWORD=<your-mysql-password>
MONGODB_URI=<your-mongodb-connection-string>
JWT_SECRET=<generated-64-char-string>
GEMINI_API_KEYS=<your-api-keys>
FRONTEND_URL=* (update later)
```

## 🎨 Frontend Deployment (Vercel)

- [ ] Created `.env.production` with backend URL
- [ ] Pushed changes to GitHub
- [ ] Imported repository to Vercel
- [ ] Configured project:
  - Root Directory: `Frontend`
  - Build Command: `npm run build`
  - Output Directory: `dist`
- [ ] Added `VITE_API_URL` environment variable
- [ ] Deployment successful
- [ ] Copied frontend URL: `_____________________`

## 🔄 Post-Deployment

- [ ] Updated `FRONTEND_URL` in Render with Vercel URL
- [ ] Backend redeployed automatically
- [ ] Tested registration
- [ ] Tested login
- [ ] Tested file upload
- [ ] Tested AI summary generation
- [ ] Tested MCQ generation
- [ ] Tested flashcard generation

## 📝 Save These URLs

**Frontend**: _____________________________________

**Backend**: _____________________________________

**GitHub**: _____________________________________

## 🎯 Share Your Project

- [ ] Added live demo link to GitHub README
- [ ] Added to resume
- [ ] Added to LinkedIn projects
- [ ] Shared with potential employers

## 🔐 Security Reminders

- [ ] Never commit `.env` files
- [ ] Never commit passwords or API keys
- [ ] Rotate Gemini API keys after deployment
- [ ] Use strong JWT secret
- [ ] Keep database credentials secure

## 📊 Monitoring Setup (Optional)

- [ ] Set up UptimeRobot for uptime monitoring
- [ ] Configure error tracking (Sentry)
- [ ] Add Google Analytics to frontend
- [ ] Set up custom domain

---

## ⚠️ Common Issues

### Build Fails on Render
- Check Java version in logs
- Verify Maven dependencies
- Check build command syntax

### Frontend Can't Connect
- Verify VITE_API_URL in Vercel
- Check CORS settings in Render
- Ensure backend is running

### Database Connection Error
- Verify connection strings
- Check IP whitelist on MongoDB
- Verify Railway database is active

---

## 🎉 Deployment Complete!

Once all boxes are checked, your EduMate application is live and ready to share with the world!

**Congratulations! 🚀**


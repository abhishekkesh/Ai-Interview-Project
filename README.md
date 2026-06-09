# 🎯 AI Interview Project

An intelligent web application that leverages Google's Generative AI to help job candidates prepare for interviews. The platform analyzes resumes, job descriptions, and candidate profiles to generate comprehensive interview reports with technical and behavioral questions, skill gap analysis, and personalized preparation plans.

---

## ✨ Features

### Core Functionality
- **AI-Powered Interview Reports** - Generate detailed interview reports using Google Gemini AI based on resume, job description, and self-description
- **Technical Question Generation** - AI-generated technical questions with interview intentions and expert answers
- **Behavioral Question Generation** - Relevant behavioral questions tailored to the specific role
- **Match Score Analysis** - Get a percentage-based match score between your profile and the job position
- **Skill Gap Identification** - Identify missing skills with severity levels (low, medium, high)
- **Personalized Preparation Plan** - Day-by-day preparation strategy with specific tasks and focus areas
- **Resume Optimization** - Generate an ATS-friendly, tailored resume as PDF based on job description
- **User Authentication** - Secure login with JWT tokens and password encryption

### User Features
- View all generated interview reports
- Download tailored resumes as PDF
- Track multiple interview preparations
- Secure account management

---

---

## 🔧 Tech Stack

### Frontend
- **React 19** - UI library
- **Vite 7** - Build tool and dev server
- **React Router 7** - Client-side routing
- **Axios** - HTTP client
- **SASS** - Styling
- **ESLint** - Code linting

### Backend
- **Node.js** - Runtime environment
- **Express 5** - Web framework
- **MongoDB & Mongoose** - Database
- **Google GenAI** - AI model integration (Gemini)
- **Puppeteer** - PDF generation from HTML
- **JWT** - Authentication
- **Bcryptjs** - Password hashing
- **Zod** - Schema validation
- **Multer** - File uploads

### AI & Services
- **Google Gemini 3 Flash Preview** - Core AI model for report generation
- **PDF Parse** - Extract text from resume PDFs
- **Puppeteer** - Convert HTML resumes to PDF

---

## 📋 API Endpoints

### Authentication Routes (`/api/auth`)
- `POST /register` - Create new user account
- `POST /login` - Login and receive JWT token
- `POST /logout` - Logout user

### Interview Routes (`/api/interview`)
- `POST /` - Generate interview report (requires: resume PDF, self description, job description)
- `GET /` - Get all interview reports for logged-in user
- `GET /report/:interviewId` - Get specific interview report by ID
- `POST /resume/pdf/:interviewReportId` - Generate and download tailored resume as PDF

📖 Usage Guide
Step 1: Create Account
Register with email and password
Login to your account
Step 2: Generate Interview Report
Navigate to the interview preparation section
Upload your resume (PDF format)
Enter your self-description (skills, experience, achievements)
Paste the job description
Click "Generate Report" to analyze with AI
Step 3: Review Report
Match Score - How well your profile aligns with the job
Technical Questions - Practice interview questions with answers
Behavioral Questions - Real-world scenario questions
Skill Gaps - Areas to improve before the interview
Preparation Plan - Day-by-day study guide
Step 4: Download Tailored Resume
Generate an optimized, ATS-friendly resume
Download as PDF file
Resume is tailored to the specific job description

🤖 How AI Report Generation Works
Resume Extraction - PDF resume text is extracted
Content Analysis - Resume, self-description, and job description are analyzed
Prompt Engineering - Data is sent to Google Gemini AI with structured schema
Structured Response - AI generates interview questions, skill gaps, and preparation plan
Data Storage - Report is saved to MongoDB with user association
PDF Generation - Resumes are generated as HTML and converted to PDF using Puppeteer

🔐 Security Features
JWT Authentication - Secure token-based authentication
Password Hashing - Bcryptjs for secure password storage
CORS Configuration - Restricted to frontend origin
Protected Routes - All interview endpoints require authentication
User Isolation - Users can only access their own reports
📦 Dependencies
Backend Key Dependencies
@google/genai: ^1.42.0
express: ^5.2.1
mongoose: ^9.2.1
jsonwebtoken: ^9.0.3
bcryptjs: ^3.0.3
puppeteer: ^24.37.5
pdf-parse: ^2.4.5
zod: ^3.25.76
multer: ^2.0.2

Frontend Key Dependencies
Code
react: ^19.2.0
vite: ^7.3.1
axios: ^1.13.5
react-router: ^7.13.0
sass: ^1.97.3
📝 Environment Variables
Backend (.env file required)
Code
MONGODB_URI=mongodb://localhost:27017/ai-interview
GOOGLE_GENAI_API_KEY=your_api_key_here
JWT_SECRET=your_secret_key_here
PORT=3000
Frontend (.env file optional)
Code
VITE_API_URL=http://localhost:3000/api
🐛 Troubleshooting
Backend won't connect to MongoDB
Verify MongoDB is running
Check MONGODB_URI in .env file
Ensure network access permissions
AI report generation fails
Verify Google GenAI API key is valid
Check API quota and billing
Ensure resume PDF is readable
Resume PDF generation issues
Ensure Puppeteer dependencies are installed
Check for sufficient disk space
Verify HTML content is well-formed
CORS errors
Verify frontend URL matches CORS configuration in Backend
Default: http://localhost:5173
📄 License
ISC License - Feel free to use this project for personal and educational purposes.

👤 Author
Abhishek Kesh
GitHub: @abhishekkesh

🎓 Learning Resources
Google GenAI Documentation
React Documentation
Express.js Guide
MongoDB Documentation
Vite Guide


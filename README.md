# Interview AI Assistant

A full-stack AI-powered interview platform that leverages artificial intelligence to generate comprehensive interview reports, analyze candidate responses, and provide detailed feedback. Built with modern web technologies for seamless user experience and robust backend performance.

## ✨ Features

- **User Authentication**: Secure signup and login with JWT tokens
- **AI-Powered Interview Analysis**: Google GenAI integration for intelligent interview report generation
- **Interview Management**: Create, conduct, and manage multiple interviews
- **Detailed Reports**: Automatic generation of technical and behavioral analysis reports
- **Skill Gap Analysis**: AI-powered identification of skill gaps and improvement areas
- **Resume Generation**: PDF export of interview reports with professional formatting
- **Real-time Processing**: Asynchronous file upload and report generation
- **Protected Routes**: Role-based access control for sensitive operations
- **Session Management**: Token blacklisting and secure session handling

## 🛠️ Tech Stack

### Backend
- **Node.js** - JavaScript runtime
- **Express.js** - Web framework
- **MongoDB** - NoSQL database
- **Google GenAI** - AI service for content generation
- **JWT** - Authentication tokens
- **Multer** - File upload handling
- **Zod** - Schema validation

### Frontend
- **React** - UI library
- **Vite** - Build tool and dev server
- **React Router** - Client-side routing
- **SCSS** - Styling
- **Context API** - State management
- **Axios** - HTTP client

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v14 or higher)
- **npm** or **yarn** package manager
- **MongoDB** (local or cloud - MongoDB Atlas)
- **Git**

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/Pratik1322/Interview-Ai-Assistant.git
cd Interview-Ai-Assistant
```

### 2. Backend Setup

```bash
cd Backend

# Install dependencies
npm install

# Create .env file
copy .env.example .env  # or create manually

# Configure your .env file with:
# - MONGODB_URI=your_mongodb_connection_string
# - JWT_SECRET=your_secret_key
# - GOOGLE_GENAI_API_KEY=your_google_genai_key
# - PORT=5000

# Start the backend server
npm start
```

The backend will run on `http://localhost:5000`

### 3. Frontend Setup

```bash
cd ../Frontend

# Install dependencies
npm install

# Create .env file (if needed)
# Configure API endpoint pointing to backend

# Start the development server
npm run dev
```

The frontend will run on `http://localhost:5173` (or shown in terminal)

## 📁 Project Structure

```
Interview-Ai-Assistant/
├── Backend/
│   ├── src/
│   │   ├── app.js                 # Express app configuration
│   │   ├── server.js              # Server entry point
│   │   ├── config/
│   │   │   └── database.js         # MongoDB connection
│   │   ├── controllers/
│   │   │   ├── auth.controller.js  # Authentication logic
│   │   │   └── interview.controller.js
│   │   ├── middlewares/
│   │   │   ├── auth.middleware.js  # JWT verification
│   │   │   └── file.middleware.js  # File upload handling
│   │   ├── models/
│   │   │   ├── user.model.js
│   │   │   ├── interviewReport.model.js
│   │   │   └── blacklist.model.js
│   │   ├── routes/
│   │   │   ├── auth.routes.js
│   │   │   └── interview.routes.js
│   │   └── services/
│   │       └── ai.service.js       # Google GenAI integration
│   └── package.json
│
├── Frontend/
│   ├── src/
│   │   ├── main.jsx                # React entry point
│   │   ├── App.jsx                 # Main component
│   │   ├── app.routes.jsx          # Route definitions
│   │   ├── features/
│   │   │   ├── auth/
│   │   │   │   ├── pages/
│   │   │   │   ├── components/
│   │   │   │   ├── hooks/
│   │   │   │   └── services/
│   │   │   └── interview/
│   │   │       ├── pages/
│   │   │       ├── hooks/
│   │   │       └── services/
│   │   └── style/
│   ├── vite.config.js
│   └── package.json
│
└── README.md
```

## 🔑 Environment Variables

### Backend (.env)

```env
# Database
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/interview-ai

# JWT
JWT_SECRET=your_super_secret_jwt_key_here

# Google GenAI
GOOGLE_GENAI_API_KEY=your_google_genai_api_key

# Server
PORT=5000
NODE_ENV=development
```

### Frontend (.env or .env.local)

```env
VITE_API_URL=http://localhost:5000/api
```

## 📖 API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `POST /api/auth/logout` - Logout user

### Interview
- `POST /api/interview/create` - Create new interview
- `GET /api/interview/list` - Get all interviews
- `GET /api/interview/:id` - Get interview details
- `POST /api/interview/analyze` - Generate AI report
- `POST /api/interview/generate-report` - Generate PDF report

## 💻 Usage

### Running the Application

1. **Start MongoDB** (if using local instance)
2. **Start Backend**: `cd Backend && npm start`
3. **Start Frontend**: `cd Frontend && npm run dev`
4. **Open Browser**: Navigate to `http://localhost:5173`

### Creating an Interview

1. Sign up or log in with your credentials
2. Navigate to the Interview section
3. Start a new interview
4. Upload candidate resume/information
5. Let AI generate analysis
6. Download the PDF report

## 🔐 Authentication

The application uses JWT (JSON Web Tokens) for authentication:
- Tokens are stored in localStorage on the frontend
- Backend verifies tokens on protected routes
- Token blacklisting for logout functionality
- Protected routes redirect unauthenticated users to login

## 🤖 AI Integration

This project uses **Google Generative AI** to:
- Analyze interview responses
- Generate technical assessment reports
- Identify skill gaps
- Provide preparation recommendations
- Create structured feedback

Get your API key from: [Google AI Studio](https://makersuite.google.com/app/apikey)

## 📦 Build for Production

### Backend
```bash
cd Backend
npm start
```

### Frontend
```bash
cd Frontend
npm run build
# Output will be in dist/ folder
```

## 🧪 Testing

```bash
# Backend tests (if configured)
cd Backend
npm test

# Frontend tests (if configured)
cd Frontend
npm test
```

## 📝 Development Guidelines

- Use `.env` files for sensitive configuration
- Never commit `.env` or `node_modules`
- Follow commit message conventions: `feat:`, `fix:`, `style:`, `docs:`, etc.
- Keep code modular and DRY (Don't Repeat Yourself)
- Add comments for complex logic

## 🐛 Troubleshooting

### Port Already in Use
```bash
# Find and kill process using port 5000
lsof -i :5000
kill -9 <PID>
```

### MongoDB Connection Error
- Verify MongoDB is running
- Check connection string in `.env`
- Ensure IP whitelist includes your machine (if using MongoDB Atlas)

### API Key Errors
- Verify Google GenAI API key is valid
- Check API quotas in Google Cloud Console
- Ensure API is enabled for your project




## 👨‍💻 Author

**Pratik Shinde**
- GitHub: [@Pratik1322](https://github.com/Pratik1322)
- Email: shindepratik7886@gmail.com



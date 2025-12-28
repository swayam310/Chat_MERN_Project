# 💬 Full Stack Realtime Chat Application

A modern, real-time chat application built with the MERN stack, featuring instant messaging, online user status, image sharing, and a beautiful UI.


## ✨ Features

- 🔐 **Authentication & Authorization** - Secure JWT-based authentication with protected routes
- 💬 **Real-time Messaging** - Instant message delivery using Socket.io
- 👥 **Online User Status** - See who's online in real-time
- 🖼️ **Image Sharing** - Send and receive images in chat
- 🎨 **Modern UI** - Beautiful interface built with TailwindCSS and DaisyUI
- 🌓 **Theme Support** - Dark/Light theme toggle
- 📱 **Responsive Design** - Works seamlessly on desktop and mobile devices
- 🔄 **State Management** - Efficient state management with Zustand
- ⚡ **Fast Performance** - Optimized with React and Vite
- 🛡️ **Error Handling** - Comprehensive error handling on both client and server

## 🛠️ Tech Stack

### Frontend
- **React 18** - UI library
- **Vite** - Build tool and dev server
- **React Router DOM** - Client-side routing
- **Socket.io Client** - Real-time communication
- **Zustand** - State management
- **TailwindCSS** - Utility-first CSS framework
- **DaisyUI** - Component library for TailwindCSS
- **Axios** - HTTP client
- **React Hot Toast** - Toast notifications
- **Lucide React** - Icon library

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **Socket.io** - Real-time bidirectional communication
- **MongoDB** - NoSQL database
- **Mongoose** - MongoDB object modeling
- **JWT** - Authentication tokens
- **Bcryptjs** - Password hashing
- **Cloudinary** - Image upload and storage
- **Cookie Parser** - Cookie parsing middleware
- **CORS** - Cross-origin resource sharing

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v14 or higher)
- **npm** or **yarn**
- **MongoDB** (local or cloud instance like MongoDB Atlas)
- **Cloudinary Account** (for image uploads)

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/swayam310/Chat_MERN_Project.git
cd Chat_MERN_Project
```

### 2. Install Dependencies

Install dependencies for both frontend and backend:

```bash
# Install root dependencies
npm install

# This will install dependencies for both frontend and backend
npm run build
```

Or install separately:

```bash
# Backend dependencies
cd backend
npm install

# Frontend dependencies
cd ../frontend
npm install
```

### 3. Environment Variables

Create a `.env` file in the `backend` directory:

```env
# Database
MONGODB_URI=your_mongodb_connection_string

# Server
PORT=5001
NODE_ENV=development

# JWT Secret
JWT_SECRET=your_jwt_secret_key

# Cloudinary (for image uploads)
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
```

### 4. Run the Application

#### Development Mode

**Backend:**
```bash
cd backend
npm run dev
```

**Frontend:**
```bash
cd frontend
npm run dev
```

The backend will run on `http://localhost:5001` and frontend on `http://localhost:5173`

#### Production Mode

Build and start the application:

```bash
# Build the frontend
npm run build

# Start the server (serves both backend API and frontend)
npm start
```

## 📁 Project Structure

```
fullstack-chat-app/
├── backend/
│   ├── src/
│   │   ├── controllers/      # Request handlers
│   │   │   ├── auth.controller.js
│   │   │   └── message.controller.js
│   │   ├── lib/              # Utility libraries
│   │   │   ├── cloudinary.js
│   │   │   ├── db.js
│   │   │   ├── socket.js
│   │   │   └── utils.js
│   │   ├── middleware/       # Custom middleware
│   │   │   └── auth.middleware.js
│   │   ├── models/           # Database models
│   │   │   ├── message.model.js
│   │   │   └── user.model.js
│   │   ├── routes/           # API routes
│   │   │   ├── auth.route.js
│   │   │   └── message.route.js
│   │   ├── seeds/            # Database seeds
│   │   │   └── user.seed.js
│   │   └── index.js          # Entry point
│   └── package.json
├── frontend/
│   ├── src/
│   │   ├── components/       # React components
│   │   │   ├── ChatContainer.jsx
│   │   │   ├── ChatHeader.jsx
│   │   │   ├── MessageInput.jsx
│   │   │   ├── Navbar.jsx
│   │   │   ├── Sidebar.jsx
│   │   │   └── skeletons/    # Loading skeletons
│   │   ├── pages/            # Page components
│   │   │   ├── HomePage.jsx
│   │   │   ├── LoginPage.jsx
│   │   │   ├── SignUpPage.jsx
│   │   │   ├── ProfilePage.jsx
│   │   │   └── SettingsPage.jsx
│   │   ├── store/            # Zustand stores
│   │   │   ├── useAuthStore.js
│   │   │   ├── useChatStore.js
│   │   │   └── useThemeStore.js
│   │   ├── lib/              # Utilities
│   │   │   ├── axios.js
│   │   │   └── utils.js
│   │   ├── constants/        # Constants
│   │   ├── App.jsx
│   │   └── main.jsx
│   └── package.json
└── README.md
```

## 🔌 API Endpoints

### Authentication Routes (`/api/auth`)

- `POST /api/auth/signup` - Register a new user
- `POST /api/auth/login` - Login user
- `POST /api/auth/logout` - Logout user
- `GET /api/auth/check` - Check authentication status
- `PUT /api/auth/update-profile` - Update user profile (protected)

### Message Routes (`/api/messages`)

- `GET /api/messages/users` - Get all users for sidebar (protected)
- `GET /api/messages/:id` - Get messages with a specific user (protected)
- `POST /api/messages/send/:id` - Send a message to a user (protected)

## 🎯 Key Features Explained

### Real-time Communication
- Uses Socket.io for bidirectional real-time communication
- Messages are instantly delivered to connected users
- Online user status is updated in real-time

### Authentication Flow
- JWT tokens stored in HTTP-only cookies for security
- Protected routes require valid authentication
- Automatic token refresh and validation

### Image Upload
- Images are uploaded to Cloudinary
- Supports image preview before sending
- Optimized image handling and storage

### State Management
- Zustand stores for:
  - Authentication state (`useAuthStore`)
  - Chat and messages (`useChatStore`)
  - Theme preferences (`useThemeStore`)

## 🧪 Development

### Running in Development Mode

1. Start MongoDB (if running locally)
2. Set up environment variables in `backend/.env`
3. Run backend: `cd backend && npm run dev`
4. Run frontend: `cd frontend && npm run dev`

### Building for Production

```bash
npm run build
```

This will:
- Install all dependencies
- Build the React frontend
- Prepare the app for production deployment

## 🚢 Deployment

The application is configured to serve the frontend build from the Express server in production mode. You can deploy to:

- **Heroku**
- **Vercel** (frontend) + **Railway/Render** (backend)
- **AWS**
- **DigitalOcean**
- Any Node.js hosting platform

Make sure to set `NODE_ENV=production` in your production environment variables.

## 📝 License

This project is licensed under the ISC License.

## 👤 Author

**Swayam310**

- GitHub: [@swayam310](https://github.com/swayam310)

## 🙏 Acknowledgments

- Built with modern web technologies
- Inspired by popular chat applications
- Uses open-source libraries and frameworks

## 📞 Support

If you have any questions or run into issues, please open an issue on the GitHub repository.

---

⭐ If you found this project helpful, please consider giving it a star!



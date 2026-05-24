# LinkedIn Clone - Social Network

A full-stack social network application inspired by LinkedIn, built with Node.js, Express, React, and MongoDB.

## 📋 Project Overview

This project is a complete LinkedIn clone featuring user authentication, profile management, connection requests, posts, and notifications. It includes both backend API and frontend UI components.

## 🏗️ Project Structure

```
LinkedIn/
├── backend/          # Node.js Express API server
│   ├── config/       # Configuration files (database, cloudinary, JWT token)
│   ├── controllers/  # Route controllers for business logic
│   ├── middlewares/  # Custom middleware (authentication, multer)
│   ├── models/       # MongoDB schemas (user, post, connection, notification)
│   ├── routes/       # API route definitions
│   ├── public/       # Static files
│   ├── index.js      # Server entry point
│   └── package.json  # Backend dependencies
│
└── frontend/         # React Vite application
    ├── src/
    │   ├── components/  # Reusable React components
    │   ├── pages/       # Page components (Home, Profile, Network, etc.)
    │   ├── context/     # React Context (Auth, User)
    │   ├── assets/      # Images and static assets
    │   ├── App.jsx      # Main App component
    │   └── main.jsx     # React entry point
    ├── public/          # Static assets
    ├── vite.config.js   # Vite configuration
    ├── tailwind.config.js # Tailwind CSS configuration
    ├── package.json     # Frontend dependencies
    └── index.html       # HTML template
```

## 🚀 Quick Start

### Prerequisites
- Node.js (v14 or higher)
- MongoDB
- Cloudinary account (for image uploads)
- Git

### Backend Setup

1. Navigate to the backend directory:
```bash
cd backend
```

2. Install dependencies:
```bash
npm install
```

3. Create a `.env` file with the following variables:
```
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
CLOUDINARY_NAME=your_cloudinary_name
CLOUDINARY_KEY=your_cloudinary_key
CLOUDINARY_SECRET=your_cloudinary_secret
PORT=5000
```

4. Start the backend server:
```bash
npm start
```

The backend will run on `http://localhost:5000`

### Frontend Setup

1. Navigate to the frontend directory:
```bash
cd frontend
```

2. Install dependencies:
```bash
npm install
```

3. Create a `.env` file with:
```
VITE_API_URL=http://localhost:5000
```

4. Start the development server:
```bash
npm run dev
```

The frontend will run on `http://localhost:5173`

## 📚 Features

- **User Authentication**: Register and login with JWT tokens
- **Profile Management**: Create and edit user profiles
- **Connections**: Send, accept, and manage connection requests
- **Posts**: Create, read, update, and delete posts
- **Notifications**: Real-time notifications for connections and interactions
- **Image Upload**: Upload profile pictures and post images via Cloudinary
- **Responsive Design**: Mobile-friendly UI with Tailwind CSS

## 🛠️ Tech Stack

### Backend
- **Runtime**: Node.js
- **Framework**: Express.js
- **Database**: MongoDB
- **Authentication**: JWT (JSON Web Tokens)
- **Image Storage**: Cloudinary
- **Middleware**: Multer (for file uploads)

### Frontend
- **Framework**: React
- **Build Tool**: Vite
- **Styling**: Tailwind CSS
- **State Management**: React Context
- **HTTP Client**: Axios

## 📁 API Routes

### Authentication
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login user
- `POST /api/auth/logout` - Logout user

### User
- `GET /api/user/profile` - Get user profile
- `PUT /api/user/profile` - Update user profile
- `GET /api/user/:id` - Get user by ID

### Connections
- `POST /api/connection/request` - Send connection request
- `GET /api/connection/requests` - Get pending requests
- `POST /api/connection/accept` - Accept connection request
- `DELETE /api/connection/:id` - Remove connection

### Posts
- `GET /api/post` - Get all posts
- `POST /api/post` - Create a new post
- `PUT /api/post/:id` - Update post
- `DELETE /api/post/:id` - Delete post

### Notifications
- `GET /api/notification` - Get all notifications
- `PUT /api/notification/:id` - Mark notification as read

## 🔐 Security

- JWT-based authentication for API security
- Password hashing using bcrypt
- CORS configuration for frontend-backend communication
- Environment variables for sensitive data

## 📦 Dependencies

### Key Backend Dependencies
- express
- mongoose
- jsonwebtoken
- bcryptjs
- multer
- cloudinary

### Key Frontend Dependencies
- react
- vite
- tailwindcss
- axios
- react-router-dom

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is open source and available under the MIT License.

## 👨‍💻 Author

Created by n30kumar

## 🔗 Links

- GitHub: https://github.com/n30kumar/-LinkedIn-Clone_social_network.git
- LinkedIn: [Your LinkedIn Profile]

## 💡 Future Enhancements

- [ ] Real-time notifications using Socket.io
- [ ] Messaging between users
- [ ] Job postings and applications
- [ ] Advanced search functionality
- [ ] Recommendation system
- [ ] Analytics dashboard

## 📞 Support

For support, email your-email@example.com or open an issue on GitHub.

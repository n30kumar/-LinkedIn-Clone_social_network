# LinkedIn Clone - Backend API

Node.js Express server for the LinkedIn Clone social network application. This API handles authentication, user profiles, connections, posts, and notifications.

## 📋 Overview

This is the backend API server that powers the LinkedIn Clone application. It provides RESTful endpoints for all frontend operations and integrates with MongoDB for data persistence and Cloudinary for image storage.

## 🚀 Getting Started

### Prerequisites
- Node.js (v14 or higher)
- MongoDB (local or cloud instance)
- Cloudinary account (for image uploads)
- npm or yarn

### Installation

1. Navigate to the backend directory:
```bash
cd backend
```

2. Install dependencies:
```bash
npm install
```

3. Create a `.env` file in the backend root directory:
```
PORT=5000
MONGODB_URI=mongodb://localhost:27017/linkedin_clone
JWT_SECRET=your_super_secret_jwt_key_change_this
CLOUDINARY_NAME=your_cloudinary_name
CLOUDINARY_KEY=your_cloudinary_api_key
CLOUDINARY_SECRET=your_cloudinary_api_secret
NODE_ENV=development
```

4. Start the server:
```bash
npm start
```

The server will run on `http://localhost:5000`

## 📁 Project Structure

```
backend/
├── config/
│   ├── db.js              # MongoDB connection
│   ├── cloudinary.js      # Cloudinary configuration
│   └── token.js           # JWT token utilities
├── controllers/
│   ├── auth.controllers.js          # Auth logic (register, login)
│   ├── user.controllers.js          # User profile logic
│   ├── post.Controllers.js          # Post CRUD operations
│   ├── connection.controllers.js    # Connection requests logic
│   └── notification.controllers.js  # Notification logic
├── models/
│   ├── user.model.js          # User schema
│   ├── post.model.js          # Post schema
│   ├── connection.model.js    # Connection schema
│   └── notification.model.js  # Notification schema
├── middlewares/
│   ├── isAuth.js       # JWT authentication middleware
│   └── multer.js       # File upload middleware
├── routes/
│   ├── auth.routes.js          # Authentication endpoints
│   ├── user.routes.js          # User endpoints
│   ├── post.routes.js          # Post endpoints
│   ├── connection.routes.js    # Connection endpoints
│   └── notification.routes.js  # Notification endpoints
├── public/            # Static files
├── index.js           # Server entry point
├── package.json       # Dependencies
└── .env              # Environment variables (not in git)
```

## 🔌 API Endpoints

### Authentication Routes (`/api/auth`)
- `POST /register` - Register a new user
  - Body: `{ email, password, firstName, lastName }`
  - Returns: User object with token

- `POST /login` - Login user
  - Body: `{ email, password }`
  - Returns: User object with token

- `POST /logout` - Logout user
  - Returns: Success message

### User Routes (`/api/user`)
- `GET /profile` - Get current user profile (requires auth)
  - Returns: User profile data

- `GET /:id` - Get user by ID (requires auth)
  - Params: `id` - User ID
  - Returns: User profile data

- `PUT /profile` - Update current user profile (requires auth)
  - Body: User data to update
  - Returns: Updated user object

- `POST /avatar` - Upload user avatar (requires auth)
  - Body: FormData with image
  - Returns: User object with new avatar URL

### Post Routes (`/api/post`)
- `GET /` - Get all posts (requires auth)
  - Query: `page`, `limit`
  - Returns: Array of posts with pagination

- `POST /` - Create a new post (requires auth)
  - Body: `{ content, image }`
  - Returns: Created post object

- `PUT /:id` - Update a post (requires auth)
  - Params: `id` - Post ID
  - Body: Updated post data
  - Returns: Updated post object

- `DELETE /:id` - Delete a post (requires auth)
  - Params: `id` - Post ID
  - Returns: Success message

- `POST /:id/like` - Like/unlike a post (requires auth)
  - Params: `id` - Post ID
  - Returns: Updated post object

### Connection Routes (`/api/connection`)
- `POST /request` - Send connection request (requires auth)
  - Body: `{ userId }`
  - Returns: Connection request object

- `GET /requests` - Get pending connection requests (requires auth)
  - Returns: Array of pending requests

- `POST /accept` - Accept connection request (requires auth)
  - Body: `{ requestId }`
  - Returns: Success message

- `DELETE /:id` - Remove connection (requires auth)
  - Params: `id` - Connection ID
  - Returns: Success message

- `GET /` - Get all connections (requires auth)
  - Returns: Array of connected users

### Notification Routes (`/api/notification`)
- `GET /` - Get all notifications (requires auth)
  - Returns: Array of notifications

- `PUT /:id` - Mark notification as read (requires auth)
  - Params: `id` - Notification ID
  - Returns: Updated notification

- `DELETE /:id` - Delete notification (requires auth)
  - Params: `id` - Notification ID
  - Returns: Success message

## 🔐 Middleware

### isAuth.js
Authentication middleware that verifies JWT tokens in request headers.
- Extracts token from `Authorization` header
- Verifies token validity
- Attaches user data to request object
- Used on protected routes

### multer.js
File upload middleware for handling image uploads.
- Configures file size limits
- Validates file types (images only)
- Stores files temporarily before upload to Cloudinary

## 📊 Database Models

### User Model
- email (unique)
- password (hashed)
- firstName
- lastName
- profilePicture
- bio
- location
- skills
- createdAt
- updatedAt

### Post Model
- userId (reference to User)
- content
- image
- likes (array of user IDs)
- comments (array)
- createdAt
- updatedAt

### Connection Model
- userId (requester)
- targetUserId (receiver)
- status (pending/accepted/rejected)
- createdAt

### Notification Model
- userId (recipient)
- fromUserId (sender)
- type (connection_request/post_like/comment)
- relatedId (post/connection ID)
- isRead
- createdAt

## 🔧 Configuration Files

### config/db.js
MongoDB connection setup using Mongoose.

### config/cloudinary.js
Cloudinary image upload configuration.

### config/token.js
JWT token generation and verification utilities.

## 📦 Dependencies

- **express** - Web framework
- **mongoose** - MongoDB ODM
- **jsonwebtoken** - JWT handling
- **bcryptjs** - Password hashing
- **multer** - File upload handling
- **cloudinary** - Image storage service
- **dotenv** - Environment variables
- **cors** - Cross-Origin Resource Sharing
- **helmet** - Security headers

## 🧪 Testing

To test API endpoints, use tools like:
- Postman
- Insomnia
- cURL
- Thunder Client (VS Code extension)

## 🚨 Error Handling

The API returns standard HTTP status codes:
- `200` - Success
- `201` - Created
- `400` - Bad Request
- `401` - Unauthorized
- `403` - Forbidden
- `404` - Not Found
- `500` - Server Error

## 🔒 Security Best Practices

- Passwords are hashed using bcryptjs
- Sensitive data stored in .env file
- CORS configured for specific origins
- JWT tokens for stateless authentication
- Input validation on all endpoints
- Rate limiting recommended for production

## 🚀 Deployment

### Using Heroku
1. Create a Heroku app
2. Set environment variables
3. Push code to Heroku
4. MongoDB Atlas for cloud database

### Using Railway
1. Connect GitHub repository
2. Set environment variables
3. Auto-deploy on push

### Using DigitalOcean
1. Create a droplet
2. Install Node.js and MongoDB
3. Clone repository
4. Set environment variables
5. Use PM2 for process management

## 📝 Environment Variables

Required environment variables for `.env` file:
```
PORT                 # Server port (default: 5000)
MONGODB_URI          # MongoDB connection string
JWT_SECRET           # JWT signing secret
CLOUDINARY_NAME      # Cloudinary account name
CLOUDINARY_KEY       # Cloudinary API key
CLOUDINARY_SECRET    # Cloudinary API secret
NODE_ENV             # development/production
```

## 🤝 Contributing

1. Create a new branch
2. Make your changes
3. Test thoroughly
4. Submit a pull request

## 📞 Support

For issues or questions, open an issue on the GitHub repository.

## 📄 License

MIT License - see LICENSE file for details

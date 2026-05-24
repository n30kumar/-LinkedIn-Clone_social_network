# LinkedIn Clone - Frontend

A modern React application built with Vite and Tailwind CSS for the LinkedIn Clone social network.

## 📋 Overview

This is the frontend of the LinkedIn Clone project. It provides a responsive user interface for all social networking features including user profiles, connections, posts, and notifications.

## 🚀 Getting Started

### Prerequisites
- Node.js (v14 or higher)
- npm or yarn
- Backend server running on http://localhost:5000

### Installation

1. Navigate to the frontend directory:
```bash
cd frontend
```

2. Install dependencies:
```bash
npm install
```

3. Create a `.env` file in the frontend root directory:
```
VITE_API_URL=http://localhost:5000
VITE_APP_NAME=LinkedIn Clone
```

4. Start the development server:
```bash
npm run dev
```

The frontend will be available at `http://localhost:5173`

## 📁 Project Structure

```
frontend/
├── src/
│   ├── components/
│   │   ├── ConnectionButton.jsx      # Connection request button
│   │   ├── EditProfile.jsx           # Profile edit modal
│   │   ├── Nav.jsx                   # Navigation bar
│   │   └── Post.jsx                  # Post component
│   ├── pages/
│   │   ├── Home.jsx                  # Home feed page
│   │   ├── Login.jsx                 # Login page
│   │   ├── Signup.jsx                # User registration page
│   │   ├── Profile.jsx               # User profile page
│   │   ├── Network.jsx               # Connections/network page
│   │   └── Notification.jsx          # Notifications page
│   ├── context/
│   │   ├── AuthContext.jsx           # Authentication context
│   │   └── UserContext.jsx           # User data context
│   ├── assets/                       # Images and static assets
│   ├── App.jsx                       # Main app component
│   ├── index.css                     # Global styles
│   └── main.jsx                      # React entry point
├── public/                           # Static assets
├── index.html                        # HTML template
├── vite.config.js                    # Vite configuration
├── tailwind.config.js                # Tailwind CSS configuration
├── postcss.config.js                 # PostCSS configuration
├── eslint.config.js                  # ESLint configuration
├── package.json                      # Dependencies
└── .env                              # Environment variables (not in git)
```

## 📚 Pages

### Home Page (`/`)
- Displays feed of posts from connected users
- Create new posts
- Like and comment on posts
- Real-time updates

### Login Page (`/login`)
- User authentication
- Email and password input
- Link to signup page
- JWT token handling

### Signup Page (`/signup`)
- New user registration
- Form validation
- Password confirmation
- Auto-login after registration

### Profile Page (`/profile/:id`)
- View user profile
- Edit profile information
- Upload profile picture
- Display user's posts
- Connection status button

### Network Page (`/network`)
- View all connections
- See pending connection requests
- Accept/reject connection requests
- Disconnect from users
- Search users to connect

### Notification Page (`/notifications`)
- View all notifications
- Mark as read
- Delete notifications
- Filter notifications by type

## 🎨 Components

### Nav.jsx
Main navigation bar with:
- Logo
- Navigation links
- User menu
- Search functionality
- Logout button

### Post.jsx
Reusable post component displaying:
- User information
- Post content
- Images
- Like count
- Comment section
- Share functionality

### ConnectionButton.jsx
Interactive button for:
- Sending connection requests
- Accepting connections
- Removing connections

### EditProfile.jsx
Modal dialog for:
- Editing profile information
- Uploading profile picture
- Updating bio and skills

## 🔄 State Management

### AuthContext
Manages global authentication state:
- User authentication status
- JWT token
- Login/Logout functions
- Token persistence

### UserContext
Manages user data:
- Current user profile
- User posts
- Connections
- Notifications

## 🎨 Styling

The project uses **Tailwind CSS** for styling:
- Responsive design
- Utility-first approach
- Custom color schemes
- Mobile-first layout

## 🛠️ Available Scripts

```bash
# Start development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview

# Run ESLint
npm run lint

# Fix ESLint issues
npm run lint:fix
```

## 📦 Dependencies

### Key Dependencies
- **react** - UI library
- **vite** - Build tool and dev server
- **tailwindcss** - Utility-first CSS framework
- **axios** - HTTP client
- **react-router-dom** - Client-side routing
- **lucide-react** - Icon library

### Dev Dependencies
- **@vitejs/plugin-react** - React plugin for Vite
- **eslint** - Code quality tool
- **postcss** - CSS processor
- **autoprefixer** - PostCSS plugin

## 🔌 API Integration

The frontend communicates with the backend API at `http://localhost:5000`.

### Example API Calls

```javascript
// Login
POST /api/auth/login
{ email, password }

// Get user profile
GET /api/user/profile

// Create post
POST /api/post
{ content, image }

// Send connection request
POST /api/connection/request
{ userId }

// Get notifications
GET /api/notification
```

## 🔐 Authentication

- JWT tokens stored in localStorage
- Token included in Authorization header for requests
- Automatic logout on token expiration
- Protected routes redirect to login

## 📱 Responsive Design

The application is fully responsive with:
- Mobile-first approach
- Breakpoints for tablet and desktop
- Touch-friendly interface
- Optimized performance

## 🚀 Performance Optimizations

- Code splitting with Vite
- Lazy loading of components
- Image optimization
- Caching strategies
- Minimized bundle size

## 🧪 Best Practices

- Component-based architecture
- Context API for state management
- Error handling and validation
- Loading states
- User feedback messages

## 🔗 Environment Variables

Required environment variables for `.env` file:
```
VITE_API_URL          # Backend API base URL
VITE_APP_NAME         # Application name
```

## 🐛 Debugging

Enable debugging:
1. Use browser DevTools (F12)
2. Check Console for errors
3. Use React DevTools extension
4. Check Network tab for API calls

## 🚀 Deployment

### Vercel
```bash
npm run build
vercel --prod
```

### Netlify
```bash
npm run build
netlify deploy --prod --dir=dist
```

### GitHub Pages
```bash
npm run build
# Push dist folder to gh-pages branch
```

## 📋 Features

- ✅ User authentication (Login/Signup)
- ✅ Profile management
- ✅ Create, edit, delete posts
- ✅ Like and comment on posts
- ✅ Connection requests
- ✅ User network/connections
- ✅ Notifications
- ✅ Profile picture upload
- ✅ Responsive design
- ✅ Real-time interactions

## 🤝 Contributing

1. Create a feature branch
2. Make your changes
3. Test thoroughly
4. Submit a pull request

## 🐛 Known Issues

- List any known issues here
- Workarounds if applicable

## 🔄 Future Enhancements

- [ ] Real-time notifications with Socket.io
- [ ] Messaging system
- [ ] Advanced search
- [ ] Dark mode
- [ ] Analytics dashboard
- [ ] Job postings
- [ ] Recommendations

## 📞 Support

For issues or questions:
1. Check existing GitHub issues
2. Open a new issue with details
3. Include error messages and steps to reproduce

## 📄 License

MIT License - see LICENSE file for details

## 👨‍💻 Author

Created by n30kumar

## 🔗 Related Projects

- [Backend Repository](https://github.com/n30kumar/-LinkedIn-Clone_social_network.git)
- [Main Repository](https://github.com/n30kumar/-LinkedIn-Clone_social_network.git)

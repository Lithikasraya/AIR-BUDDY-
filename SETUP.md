# Ether IoT Dashboard - Setup Guide

## 🎯 Quick Start

### 1. Install Dependencies
```bash
npm install
```

### 2. Start Development Server
```bash
npm run dev
```

### 3. Open Browser
Navigate to `http://localhost:3000`

### 4. Login
- Email: any@email.com (or any email)
- Password: any password
- (Mock authentication enabled)

---

## 📂 Project Structure

```
ether-iot-dashboard/
│
├── src/
│   ├── components/              # Reusable UI components
│   │   ├── Button.jsx          # Custom button component
│   │   ├── Input.jsx           # Form input component
│   │   ├── MetricCard.jsx      # Metric display card
│   │   ├── GlassCard.jsx       # Glass effect container
│   │   ├── ThemeToggle.jsx     # Dark/light mode toggle
│   │   ├── Sidebar.jsx         # Left navigation sidebar
│   │   ├── Navbar.jsx          # Top navigation bar
│   │   ├── MainLayout.jsx      # Main app layout wrapper
│   │   └── ProtectedRoute.jsx  # Authentication wrapper
│   │
│   ├── pages/                  # Page components
│   │   ├── Login.jsx           # Authentication page
│   │   ├── Dashboard.jsx       # Main dashboard with charts
│   │   ├── Alerts.jsx          # Alert management page
│   │   ├── Settings.jsx        # Settings & configuration
│   │   └── Admin.jsx           # Admin panel
│   │
│   ├── context/                # State management
│   │   ├── ThemeContext.jsx    # Theme state (dark/light)
│   │   ├── AuthContext.jsx     # Authentication state
│   │   └── SensorContext.jsx   # Sensor data state
│   │
│   ├── utils/                  # Utilities
│   │   └── api.js              # Axios API client
│   │
│   ├── App.jsx                 # Main app component
│   ├── main.jsx                # React entry point
│   └── index.css               # Global styles
│
├── public/                     # Static assets
├── .gitignore                  # Git ignore rules
├── .env.example                # Environment variables template
├── package.json                # Dependencies
├── vite.config.js              # Vite configuration
├── tailwind.config.js          # Tailwind CSS config
├── postcss.config.js           # PostCSS config
├── index.html                  # HTML entry point
├── README.md                   # Project documentation
└── SETUP.md                    # This file
```

---

## 🎨 Design Features

### Color Scheme
- **Primary**: Blue gradient
- **Background**: Dark blue gradient (#0A192F → #020C1B)
- **Glass Effect**: Semi-transparent with backdrop blur
- **Status Colors**: Green (normal), Yellow (warning), Red (critical)

### Components
- Glassmorphism design with rounded corners (24px+)
- Smooth animations using Framer Motion
- Responsive grid layouts
- Soft glow shadows

---

## 🔐 Authentication

### Features
- Login page with email/password
- Protected routes (auto-redirect to login if not authenticated)
- User state management
- Persistent user data (localStorage)

### Login Details
All credentials work (mock auth). Example:
- Email: `test@example.com`
- Password: `password123`

---

## 📊 Pages Overview

### Dashboard
- 6 metric cards (Temperature, Humidity, PM2.5, PM10, Sound, CO₂)
- Line chart (Air quality trends)
- Bar chart (Sensor comparison)
- System status indicator

### Alerts
- List of system alerts
- Color-coded by severity (Critical/Warning/Info)
- Timestamps and locations
- Delete/filter functionality

### Settings
- Profile management
- Theme toggle (dark/light)
- Device configuration
- API key management
- Notification preferences
- Two-factor authentication setup

### Admin
- User management table
- User statistics (Total, Active, Inactive, Admins)
- Search functionality
- Edit/Delete user actions
- Role-based display

---

## ⚙️ Configuration

### Environment Variables
Create a `.env.local` file:
```
VITE_API_URL=http://localhost:3001/api
VITE_ENABLE_DARK_MODE=true
```

### Tailwind CSS
- Config: `tailwind.config.js`
- Extended colors, shadows, and animations
- Dark mode support

### API Client (Axios)
Located in `src/utils/api.js`:
- Auto-includes auth tokens
- Error handling (401 redirects to login)
- Pre-built endpoints for:
  - Authentication
  - Sensors
  - Settings
  - Admin

---

## 🚀 Development

### Available Scripts
```bash
npm run dev      # Start development server
npm run build    # Build for production
npm run preview  # Preview production build
```

### Adding New Pages
1. Create component in `src/pages/`
2. Add route in `src/App.jsx`
3. Add menu item in `src/components/Sidebar.jsx`

### Adding New Components
1. Create component in `src/components/`
2. Use Tailwind classes for styling
3. Use Framer Motion for animations
4. Import and use in pages

---

## 📱 Responsive Design

The design is fully responsive:
- **Desktop**: Full sidebar, main content
- **Tablet**: Optimized grid layouts
- **Mobile**: Stacked layouts, collapsible sidebar

---

## 🎬 Animations

Using Framer Motion:
- Page transitions
- Hover effects on cards and buttons
- Metric value animations
- Floating background elements
- Smooth scrolling

---

## 🔌 API Integration

Ready for backend integration:

```javascript
// Import API methods
import { authAPI, sensorAPI, settingsAPI, adminAPI } from './utils/api';

// Example usage
const login = async (email, password) => {
  const response = await authAPI.login(email, password);
  return response.data;
};

const getMetrics = async () => {
  const response = await sensorAPI.getMetrics();
  return response.data;
};
```

---

## 🐛 Troubleshooting

### Port 3000 Already in Use
```bash
npm run dev -- --port 3001
```

### Styles Not Showing
- Check Tailwind config content paths
- Rebuild CSS: `npm run dev`

### Components Not Importing
- Verify file paths
- Check for circular imports

### API Errors
- Check `.env.local` API URL
- Verify backend is running
- Check CORS settings on backend

---

## 📦 Build & Deployment

### Production Build
```bash
npm run build
# Creates optimized dist/ folder
```

### Deploy to Vercel
```bash
npm install -g vercel
vercel
```

### Deploy to Netlify
```bash
npm run build
# Drag & drop 'dist' folder to Netlify
```

---

## 📚 Learn More

- [React Documentation](https://react.dev)
- [Vite Guide](https://vitejs.dev)
- [Tailwind CSS](https://tailwindcss.com)
- [Framer Motion](https://www.framer.com/motion)
- [React Router](https://reactrouter.com)

---

## 💡 Next Steps

1. Replace mock authentication with real API
2. Connect to actual sensor/IoT backend
3. Implement real-time WebSocket updates
4. Add user preferences to backend
5. Implement actual 2FA
6. Add data export functionality
7. Create mobile app version (React Native)

---

Built with ❤️ using React + Vite + Tailwind CSS

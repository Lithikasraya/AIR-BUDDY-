# Ether IoT - Air Quality Network

A modern, premium IoT SaaS dashboard frontend built with React, Vite, and Tailwind CSS.

## 🎨 Features

- **Dark Mode with Glassmorphism Design** - Premium SaaS-style UI with smooth gradients and blur effects
- **Real-time Sensor Monitoring** - Display air quality metrics with live updates
- **Interactive Charts** - Recharts integration for data visualization
- **Responsive Design** - Works seamlessly on desktop, tablet, and mobile
- **Smooth Animations** - Framer Motion for polished user interactions
- **Authentication System** - Protected routes with login/logout
- **Admin Dashboard** - User management interface
- **Settings Management** - Theme toggle, API keys, security settings
- **Alert System** - Real-time notifications and alert management

## 🛠️ Tech Stack

- **React 18** - UI framework
- **Vite** - Lightning-fast build tool
- **Tailwind CSS** - Utility-first CSS framework
- **Framer Motion** - Animation library
- **React Router DOM** - Client-side routing
- **Recharts** - Charting library
- **Axios** - HTTP client
- **Lucide React** - Icon library

## 📋 Prerequisites

- Node.js 16+ 
- npm or yarn

## 🚀 Getting Started

### 1. Install Dependencies

```bash
npm install
```

### 2. Start Development Server

```bash
npm run dev
```

The app will open automatically at `http://localhost:3000`

### 3. Build for Production

```bash
npm run build
```

### 4. Preview Production Build

```bash
npm run preview
```

## 📁 Project Structure

```
src/
├── components/          # Reusable UI components
│   ├── Button.jsx
│   ├── Input.jsx
│   ├── MetricCard.jsx
│   ├── GlassCard.jsx
│   ├── ThemeToggle.jsx
│   ├── Sidebar.jsx
│   ├── Navbar.jsx
│   ├── MainLayout.jsx
│   └── ProtectedRoute.jsx
├── pages/              # Page components
│   ├── Login.jsx
│   ├── Dashboard.jsx
│   ├── Alerts.jsx
│   ├── Settings.jsx
│   └── Admin.jsx
├── context/            # React Context for state management
│   ├── ThemeContext.jsx
│   ├── AuthContext.jsx
│   └── SensorContext.jsx
├── utils/              # Utility functions
│   └── api.js
├── App.jsx            # Main app component
├── main.jsx           # React entry point
└── index.css          # Global styles
```

## 🔐 Authentication

The app includes a login system with:
- Email/password login (with mock validation)
- Protected routes that redirect to login if unauthenticated
- User context for managing authentication state
- Persistent user data using localStorage

**Default Login:**
- Email: Any email address
- Password: Any password
- (Mock authentication - use any credentials)

## 🌗 Dark/Light Mode

- Default theme is dark mode
- Click the theme toggle icon in the navbar to switch
- Theme preference is saved in localStorage
- Light mode inverts colors while maintaining the design

## 📊 Dashboard Features

- **Metric Cards** - Temperature, Humidity, PM2.5, PM10, Sound Level, CO₂
- **Line Chart** - Air quality trends over time
- **Bar Chart** - Sensor comparison data
- **Status Indicator** - Real-time system status
- **Live Updates** - Metrics update every 5 seconds

## 🚨 Alerts Page

- List of system alerts (Critical, Warning, Info)
- Color-coded alert types
- Timestamps and location information
- Dismiss individual alerts
- Export alerts as report

## ⚙️ Settings Page

- **Account Settings** - Profile information
- **Theme Configuration** - Light/Dark mode toggle
- **Device Configuration** - Device ID, friendly name, location
- **API Security** - API key management, 2FA
- **Notification Preferences** - Toggle alerts

## 👥 Admin Dashboard

- User management table
- Search and filter functionality
- Edit/Delete user actions
- User statistics
- Role-based access control

## 🎨 Design System

### Colors
- **Primary**: Blue gradient (`from-blue-500 to-blue-700`)
- **Background**: Dark gradient (`#0A192F → #020C1B`)
- **Glass Effect**: Semi-transparent with blur
- **Text**: Light gray with white headings

### Components
- Rounded corners: `24px+` (rounded-3xl)
- Shadows: Soft glow effects
- Transitions: Smooth 300ms easing
- Hover effects: Elevated with enhanced glow

## 🔌 API Integration

The project includes an Axios setup for API calls:

```javascript
import { authAPI, sensorAPI, settingsAPI, adminAPI } from './utils/api';

// Usage example:
// const user = await authAPI.login(email, password);
// const metrics = await sensorAPI.getMetrics();
```

## 📱 Responsive Design

- Mobile-first approach
- Grid layouts adapt to screen size
- Sidebar collapses on smaller screens
- Touch-friendly buttons and interactions

## 🤝 Contributing

Feel free to submit issues and enhancement requests!

## 📄 License

MIT License - feel free to use this project for personal or commercial use.

## 🚀 Deployment

### Vercel (Recommended)
```bash
npm install -g vercel
vercel
```

### Netlify
```bash
npm run build
# Deploy the 'dist' folder to Netlify
```

### Docker
```dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build
EXPOSE 3000
CMD ["npm", "run", "preview"]
```

## 💡 Tips

- Customize colors in `tailwind.config.js`
- Add more metrics in `src/context/SensorContext.jsx`
- Extend the chart data with real API calls
- Implement actual authentication with your backend
- Use environment variables for API URLs

## 🐛 Troubleshooting

**Port already in use?**
```bash
npm run dev -- --port 3001
```

**Build errors?**
```bash
rm -rf node_modules package-lock.json
npm install
npm run build
```

**Tailwind styles not showing?**
- Ensure Tailwind classes are in content paths in `tailwind.config.js`
- Rebuild CSS with `npm run dev`

---

Built with ❤️ using React + Vite + Tailwind CSS

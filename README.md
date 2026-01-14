# गतिFlow - AI-based Traffic Management System

<div align="center">
  <img src="public/logo.png" alt="गतिFlow Logo" width="200" height="200">
  
  **गतिFlow** - Advanced AI-powered traffic management dashboard for smart cities
  
  [![React](https://img.shields.io/badge/React-18.0+-blue.svg)](https://reactjs.org/)
  [![TypeScript](https://img.shields.io/badge/TypeScript-5.0+-blue.svg)](https://www.typescriptlang.org/)
  [![Vite](https://img.shields.io/badge/Vite-5.0+-purple.svg)](https://vitejs.dev/)
  [![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-3.0+-teal.svg)](https://tailwindcss.com/)
  [![Leaflet](https://img.shields.io/badge/Leaflet-1.9+-green.svg)](https://leafletjs.com/)
</div>

## 🚀 Overview

गतिFlow is a comprehensive AI-based traffic management system designed for smart cities. It provides real-time traffic monitoring, predictive analytics, emergency response coordination, and intelligent traffic signal control through an intuitive web-based dashboard.

## ✨ Key Features

### 🗺️ **Live Traffic Monitoring**
- **Real-time Map Integration**: Interactive Leaflet.js maps with live traffic data
- **Traffic Node Visualization**: Dynamic traffic congestion indicators with severity levels
- **Region Selection**: Click-to-select monitoring areas with 1km radius coverage
- **Traffic Analytics**: Real-time vehicle count, traffic levels, and congestion patterns

### 📹 **Live Camera Feed System**
- **Multi-Camera Support**: Up to 2 simultaneous camera feeds
- **Video Management**: Intelligent video assignment and playback
- **Expandable Views**: Popup modals for detailed camera monitoring
- **Live Feed Controls**: Dynamic video allocation across intersections

### 🚦 **Smart Traffic Signal Control**
- **Intersection Management**: Control 4 traffic intersections simultaneously
- **Signal Override**: Manual control for RED, GREEN, and YELLOW signals
- **Confirmation System**: Safety popups for signal changes
- **Auto-Randomization**: Automatic signal changes every 30-60 seconds

### 📊 **Analytics Dashboard**
- **Real-time Metrics**: Live traffic statistics and performance indicators
- **Traffic Trends**: Historical data visualization and pattern analysis
- **Performance Monitoring**: System health and traffic flow optimization

### 🌤️ **Weather Integration**
- **Weather Monitoring**: Real-time weather data integration
- **Traffic Impact Analysis**: Weather-based traffic pattern predictions
- **Congestion Alerts**: Weather-related traffic disruption notifications

### 🚨 **Emergency Response**
- **Emergency Coordination**: Rapid response system for traffic incidents
- **Alert Management**: Real-time emergency notifications and updates
- **Traffic Diversion**: Emergency route management and traffic redirection

### 📅 **Event Management**
- **Event Horizon**: Special event traffic management
- **Traffic Predictions**: Event-based traffic flow forecasting
- **Route Optimization**: Dynamic routing for special events

## 🛠️ Technology Stack

### **Frontend**
- **React 18+** - Modern UI framework with hooks and functional components
- **TypeScript** - Type-safe development with enhanced IDE support
- **Vite** - Lightning-fast build tool and development server
- **Tailwind CSS** - Utility-first CSS framework for rapid UI development

### **UI Components**
- **Shadcn/ui** - Modern, accessible component library
- **Lucide React** - Beautiful, customizable icons
- **Radix UI** - Unstyled, accessible UI primitives

### **Maps & Visualization**
- **Leaflet.js** - Interactive maps with custom markers and layers
- **OpenStreetMap** - Free, open-source map tiles
- **Custom Traffic Nodes** - Dynamic traffic visualization system

### **State Management**
- **React Context** - Global state management for video feeds
- **Local Storage** - Persistent user preferences and map state
- **Custom Hooks** - Reusable state logic and side effects

### **Development Tools**
- **ESLint** - Code linting and quality assurance
- **PostCSS** - CSS processing and optimization
- **TypeScript Compiler** - Static type checking

## 🌐 API Integration

गतिFlow integrates with multiple external APIs to provide real-time traffic and weather data:

### **Traffic APIs**

#### **TomTom Traffic API**
- **Traffic Flow API**: Real-time traffic flow data for Bhubaneswar region
  - Endpoint: `https://api.tomtom.com/traffic/services/4/flowSegmentData/`
  - Provides: Current speed, free flow speed, congestion levels
  - Coverage: Bounding box `85.75,20.20,85.90,20.40` (Bhubaneswar)
  
- **Traffic Tile Layer**: Visual traffic overlay on maps
  - Endpoint: `https://api.tomtom.com/traffic/map/4/tile/flow/relative/`
  - Provides: Real-time traffic visualization with color-coded congestion
  - Integration: Leaflet tile layer with 60% opacity

#### **Overpass API (OpenStreetMap)**
- **Road Network Data**: Fetches road geometries for traffic node placement
  - Endpoint: `https://overpass-api.de/api/interpreter`
  - Provides: Road network structure, highway data
  - Used for: Intelligent traffic node generation

### **Weather APIs**

#### **OpenWeatherMap API**
- **Current Weather**: Real-time weather data for Bhubaneswar
  - Endpoint: `https://api.openweathermap.org/data/2.5/weather`
  - Provides: Temperature, humidity, wind speed, conditions
  
- **Weather Layers**: Precipitation, clouds, and temperature overlays
  - Endpoints: `https://tile.openweathermap.org/map/{layer}_new/`
  - Layers: Precipitation, clouds, temperature

#### **Open-Meteo API**
- **Precipitation Forecast**: Hourly precipitation predictions
  - Endpoint: `https://api.open-meteo.com/v1/forecast`
  - Provides: Hourly precipitation data
  - Used for: Weather-traffic impact analysis

### **API Features**
- ✅ **Real-time Data**: Live traffic flow and weather updates
- ✅ **Auto-refresh**: Traffic data refreshes every 2 minutes
- ✅ **Fallback Mode**: Simulated data when APIs are unavailable
- ✅ **Toggle Support**: Switch between live and simulated data
- ✅ **Error Handling**: Graceful degradation on API failures

### **Configuration**
API keys are configured in the codebase:
- TomTom API: `src/lib/trafficNodeService.ts`
- Weather APIs: `src/components/weather/WeatherMap.tsx`

**Note**: For production deployment, move API keys to environment variables (`.env` file).

## 🚀 Getting Started

### Prerequisites
- **Node.js** (v18.0 or higher)
- **npm** or **yarn** package manager
- **Git** for version control

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/the-rajdivyansh04/GatiFlow.git
   cd GatiFlow
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Start the development server**
   ```bash
   npm run dev
   # or
   yarn dev
   ```

4. **Open your browser**
   Navigate to `http://localhost:5173` (or the port shown in terminal)

### Build for Production

```bash
npm run build
# or
yarn build
```

The built files will be in the `dist` directory, ready for deployment.

## 📁 Project Structure

```
pulse-route-prime/
├── public/                 # Static assets
│   ├── logo.png           # गतिFlow logo
│   ├── favicon.png        # Browser favicon
│   └── videos/            # Sample video files
├── src/
│   ├── components/        # Reusable UI components
│   │   ├── dashboard/     # Dashboard-specific components
│   │   │   ├── Sidebar.tsx
│   │   │   ├── TrafficMap.tsx
│   │   │   ├── AnalyticsPanel.tsx
│   │   │   └── TrafficNotifications.tsx
│   │   ├── events/        # Event management components
│   │   ├── weather/       # Weather-related components
│   │   └── ui/           # Base UI components (Shadcn/ui)
│   ├── hooks/            # Custom React hooks
│   │   ├── useVideoState.tsx
│   │   └── use-mobile.tsx
│   ├── lib/              # Utility libraries
│   │   ├── trafficNodeService.ts
│   │   └── utils.ts
│   ├── pages/            # Main application pages
│   │   ├── Index.tsx     # Live Map
│   │   ├── Analytics.tsx # Analytics Dashboard
│   │   ├── Camera.tsx    # Live Camera Feed
│   │   ├── Emergency.tsx # Emergency Response
│   │   ├── Weather.tsx   # Weather Monitoring
│   │   └── Events.tsx    # Event Management
│   ├── App.tsx           # Main application component
│   └── main.tsx          # Application entry point
├── package.json          # Dependencies and scripts
├── tailwind.config.ts    # Tailwind CSS configuration
├── vite.config.ts        # Vite configuration
└── README.md            # This file
```

## 🎯 Core Features Deep Dive

### **Live Camera Feed System**
- **Smart Video Assignment**: Automatically assigns unique videos to intersections
- **Camera Prioritization**: Intelligent camera feed management (Camera 1 → Camera 2 → Overwrite)
- **Popup Expansion**: Modal-based expanded views for detailed monitoring
- **Video Controls**: Play, pause, and loop functionality

### **Traffic Signal Management**
- **Four Intersection Control**: Manage multiple intersections simultaneously
- **Signal Override**: Manual control with confirmation dialogs
- **Auto-Randomization**: Automatic signal changes for realistic simulation
- **Status Visualization**: Color-coded status indicators (RED/GREEN/YELLOW)

### **Interactive Map System**
- **Region Selection**: Double-click to select monitoring areas
- **Traffic Node Visualization**: Dynamic congestion indicators
- **Zoom Controls**: In/out zoom with bounds restrictions
- **State Persistence**: Remembers map position and zoom level

### **Responsive Design**
- **Mobile-First**: Optimized for all device sizes
- **Adaptive Layout**: Responsive grid system
- **Touch-Friendly**: Mobile-optimized interactions
- **Accessibility**: WCAG compliant components

## 🔧 Configuration

### **Environment Variables**
Create a `.env` file in the root directory:

```env
VITE_API_URL=your_api_url_here
VITE_MAP_TILE_URL=your_map_tile_url_here
```

### **Customization**
- **Branding**: Update `public/logo.png` and `public/favicon.png`
- **Colors**: Modify `tailwind.config.ts` for custom color schemes
- **Components**: Customize Shadcn/ui components in `src/components/ui/`

## 🚀 Deployment

### **Vercel (Recommended)**
1. Connect your GitHub repository to Vercel
2. Configure build settings:
   - Build Command: `npm run build`
   - Output Directory: `dist`
3. Deploy automatically on every push

### **Netlify**
1. Connect your GitHub repository to Netlify
2. Set build command: `npm run build`
3. Set publish directory: `dist`
4. Deploy with automatic builds

### **Traditional Hosting**
1. Run `npm run build`
2. Upload the `dist` folder to your web server
3. Configure your server to serve the built files

## 🤝 Contributing

We welcome contributions to गतिFlow! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch**: `git checkout -b feature/amazing-feature`
3. **Commit your changes**: `git commit -m 'Add amazing feature'`
4. **Push to the branch**: `git push origin feature/amazing-feature`
5. **Open a Pull Request**

### **Development Guidelines**
- Follow TypeScript best practices
- Use meaningful commit messages
- Test your changes thoroughly
- Update documentation as needed
- Follow the existing code style

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **OpenStreetMap** for providing free map tiles
- **Leaflet.js** for the excellent mapping library
- **Shadcn/ui** for the beautiful component library
- **Vite** for the fast development experience
- **React** team for the amazing framework

## 📞 Support

For support, email support@gatiflow.com or create an issue in the GitHub repository.

## 🔮 Roadmap

### **Upcoming Features**
- [ ] **Machine Learning Integration**: AI-powered traffic prediction
- [ ] **Mobile App**: Native mobile application
- [ ] **API Integration**: Real traffic data APIs
- [ ] **Multi-language Support**: Internationalization
- [ ] **Advanced Analytics**: More detailed traffic insights
- [ ] **IoT Integration**: Real sensor data integration
- [ ] **Cloud Deployment**: Scalable cloud infrastructure

---

<div align="center">
  <p>Built with ❤️ for smart cities</p>
  <p><strong>गतिFlow</strong> - Making traffic management intelligent</p>
</div>

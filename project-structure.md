# Snyxap Project Structure

This document outlines the overall structure of the Snyxap application, helping new contributors understand how the codebase is organized.

## Directory Structure

```
snyxap/
├── public/                  # Static assets
│   ├── images/              # Images and icons
│   └── favicon.ico          # Site favicon
├── src/                     # Source code
│   ├── components/          # Reusable React components
│   │   ├── Layout.tsx       # Main layout wrapper
│   │   ├── Navbar.tsx       # Navigation component
│   │   ├── Footer.tsx       # Footer component
│   │   ├── rules/           # Rules management components
│   │   └── ...              # Other components
│   ├── pages/               # Next.js pages
│   │   ├── _app.tsx         # Custom App component
│   │   ├── _document.js     # Custom Document component
│   │   ├── index.tsx        # Homepage
│   │   ├── dashboard.tsx    # Dashboard page
│   │   ├── features.tsx     # Features page
│   │   ├── connect/         # Data connection pages
│   │   │   ├── index.tsx    # Main connect page
│   │   │   ├── api.tsx      # API connection page
│   │   │   ├── database.tsx # Database connection page
│   │   │   └── ...          # Other connection pages
│   │   ├── rules-management.tsx # Rules management page
│   │   └── api/             # API routes
│   │       └── auth/        # Authentication endpoints
│   ├── styles/              # Global styles
│   │   ├── globals.css      # Global CSS
│   │   └── theme.ts         # Material-UI theme configuration
│   ├── utils/               # Utility functions
│   │   ├── dataUtils.ts     # Data processing utilities
│   │   └── createEmotionCache.ts # Emotion cache setup
│   └── types/               # TypeScript type definitions
├── .env.example             # Example environment variables
├── .eslintrc.json           # ESLint configuration
├── .gitignore               # Git ignore file
├── next.config.js           # Next.js configuration
├── package.json             # Dependencies and scripts
├── tsconfig.json            # TypeScript configuration
└── README.md                # Project documentation
```

## Key Components

### UI Components

- **Layout**: Main wrapper component providing consistent layout structure
- **Navbar**: Fixed navigation bar with links to major application areas
- **Footer**: Application footer with links and information
- **DataVisualization**: Components for rendering charts and graphs
- **RulesList**: Components for displaying and managing data quality rules

### Page Structure

- **Homepage**: Landing page with value proposition and CTA
- **Dashboard**: Main user dashboard with data metrics and recent activities
- **Features**: Showcase of platform capabilities with detailed descriptions
- **Connect Pages**: Pages for connecting to different data sources
- **Rules Management**: Interface for creating and managing data quality rules

### Authentication

The application uses NextAuth.js with Google OAuth for authentication. This provides:

- Secure user authentication
- Session management
- Protected routes

### Theme System

The dark theme is implemented using Material-UI's theming system, with customizations to match modern AI interfaces:

- Custom color palette focused on dark backgrounds
- Typography system with carefully selected font weights
- Responsive breakpoints for different device sizes
- Common component styling overrides

## Data Flow

1. User authenticates via Google OAuth
2. User connects to data sources through the connection interfaces
3. Application profiles the data using backend services (to be implemented)
4. Profiling results are displayed in the dashboard and visualization components
5. User can set up rules to monitor data quality
6. Alerts are generated when data violates quality rules (to be implemented)

## Future Architecture

As the project evolves, we plan to implement:

- Backend API with database for storing profiles and user preferences
- WebSocket connections for real-time updates
- Microservices architecture for handling different data connectors
- Caching layer for improved performance
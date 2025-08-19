# Crave App 🍽️

A location-based social discovery app for local bars and restaurants, combining the visual appeal of Instagram with real-time deal promotion.

## Features

- 📍 **Location-Based Discovery** - Find nearby restaurants and bars automatically
- 📱 **Instagram-Style Feed** - Visual content with stories and engagement features
- 🍺 **Real-Time Deals** - Live happy hours and daily specials
- 🏪 **Business Profiles** - Complete business management system
- 📊 **Analytics Dashboard** - Performance insights for businesses
- 💰 **Monetization Ready** - Promoted posts and premium accounts

## Tech Stack

### Backend
- Node.js + TypeScript
- PostgreSQL + PostGIS (geospatial queries)
- Redis (caching)
- Docker + Kubernetes
- AWS S3 (media storage)

### Mobile App
- React Native + TypeScript
- Redux Toolkit (state management)
- Firebase (analytics, push notifications)
- React Navigation

## Quick Start

1. **Clone and setup:**
```bash
git clone <your-repo>
cd crave-app
npm run setup
```

2. **Start development environment:**
```bash
# Start all services
npm run dev

# Or start individual services
npm run dev:backend  # Backend services
npm run dev:mobile   # React Native app
```

3. **Database setup:**
```bash
# Copy environment file
cp .env.example .env

# Start database
docker-compose -f infrastructure/docker-compose.yml up postgres redis -d

# Run migrations
npm run db:migrate
```

## Project Structure

```
crave-app/
├── mobile/                 # React Native app
├── backend/               # Microservices
│   ├── api-gateway/      # API Gateway & load balancing
│   ├── auth-service/     # Authentication & user management
│   ├── post-service/     # Posts & content management
│   └── business-service/ # Business profiles & management
├── infrastructure/       # Docker & Kubernetes configs
└── shared/              # Shared types & utilities
```

## Development

- `npm run dev` - Start all services
- `npm run test` - Run all tests
- `npm run lint` - Code quality checks
- `npm run build` - Production build

## Deployment

- `npm run docker:up` - Local Docker deployment
- `npm run k8s:deploy` - Kubernetes deployment

## License

MIT License

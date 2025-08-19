# Crave App Setup Instructions

## Prerequisites

- Node.js 18+
- PostgreSQL 14+ with PostGIS extension
- Redis 7+
- Docker & Docker Compose
- React Native development environment

## Step-by-Step Setup

### 1. Environment Configuration
```bash
# Copy and configure environment variables
cp .env.example .env

# Edit .env with your actual values:
# - Database credentials
# - AWS S3 credentials  
# - API keys (SendGrid, Google Maps, etc.)
```

### 2. Database Setup
```bash
# Start PostgreSQL and Redis with Docker
docker-compose -f infrastructure/docker-compose.yml up postgres redis -d

# Install dependencies
npm run install:all

# Run database migrations
npm run db:migrate
```

### 3. Mobile Development Setup

#### iOS Setup:
```bash
cd mobile/ios
pod install
cd ..
```

#### Android Setup:
- Install Android Studio and SDK
- Create virtual device or connect physical device
- Enable developer options and USB debugging

### 4. Start Development
```bash
# Terminal 1: Start backend services
npm run dev:backend

# Terminal 2: Start React Native
npm run dev:mobile

# Terminal 3: Run mobile app
cd mobile
npm run android  # For Android
npm run ios      # For iOS
```

### 5. Testing
```bash
# Run all tests
npm run test

# Test specific services
npm run test:auth
npm run test:mobile
```

## Troubleshooting

### Common Issues:

1. **Database connection errors**
   - Ensure PostgreSQL is running
   - Check DATABASE_URL in .env file

2. **React Native build errors**
   - Clean build: `cd mobile && npx react-native clean`
   - Reset Metro cache: `npx react-native start --reset-cache`

3. **iOS build issues**
   - Clean build folder in Xcode
   - Re-run `pod install`

4. **Android build issues**
   - Clean gradle: `cd mobile/android && ./gradlew clean`
   - Check Android SDK path

## Production Deployment

See deployment documentation in `/docs/deployment.md`

# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview
WOD Coach is an iOS mobile application with a Node.js backend for AI-powered workout training and coaching.

## Repository Structure
The repository is organized into two main components:
- `/ios` - iOS native application
- `/server` - Node.js backend server

## Development Environment Setup

### iOS Development Requirements
- Xcode 15.0 or later
- iOS 17.0 SDK or later
- CocoaPods for dependency management
- Swift 5.9 or later

### Backend Development Requirements
- Node.js 20.x or later
- npm 10.x or later
- TypeScript 5.x

## Common Commands

### Backend (Node.js)
```bash
# Install dependencies
npm install

# Run development server
npm run dev

# Build for production
npm run build

# Run tests
npm test

# Run specific test file
npm test -- path/to/test-file.test.ts

# Type checking
npm run type-check

# Linting
npm run lint
npm run lint:fix
```

### iOS
```bash
# Install dependencies
cd ios
pod install

# Build and run from Xcode
open ios/WODCoach.xcworkspace

# Run tests from command line
xcodebuild test -workspace ios/WODCoach.xcworkspace -scheme WODCoach -destination 'platform=iOS Simulator,name=iPhone 15'

# Run specific test class
xcodebuild test -workspace ios/WODCoach.xcworkspace -scheme WODCoach -destination 'platform=iOS Simulator,name=iPhone 15' -only-testing:WODCoachTests/TestClassName
```

## Architecture Overview

### iOS App Architecture
- MVVM (Model-View-ViewModel) architecture
- SwiftUI for UI components
- Combine framework for reactive programming
- Core Data for local persistence
- Network layer using URLSession and async/await

### Backend Architecture
- Express.js with TypeScript
- MongoDB for data persistence
- JWT for authentication
- OpenAI integration for AI training features
- REST API endpoints with OpenAPI/Swagger documentation

## Development Workflow
1. Create feature branch from `main`
2. Implement changes
3. Write tests
4. Create pull request
5. Code review
6. Merge to `main`

## Environment Configuration
- Backend: `.env` file for environment variables
- iOS: `Configuration` folder with different scheme configurations (Debug, Release)

## Testing Strategy
- Backend: Jest for unit and integration tests
- iOS: XCTest framework for unit and UI tests
- End-to-end tests using API test suite

## Logging and Monitoring
- Backend: Winston for logging
- iOS: OSLog for unified logging
- Error tracking with Sentry
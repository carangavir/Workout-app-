# PPL Core Workout Companion

## Overview

PPL Core Workout Companion is a mobile-optimized web application designed to track and guide users through a Push, Pull, Legs (PPL) workout program. The application provides structured workout templates, exercise tracking with sets, reps, and RPE (Rate of Perceived Exertion), progress monitoring, and an exercise library with detailed instructions. Built as a Progressive Web App (PWA), it focuses on delivering a seamless mobile experience for gym-goers following the PPL training methodology.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
The client is built using React with TypeScript and follows a component-based architecture. The application uses Vite as the build tool and leverages Wouter for lightweight client-side routing. The UI is built with shadcn/ui components on top of Radix UI primitives, providing accessible and customizable interface elements. TailwindCSS handles styling with a comprehensive design system supporting dark mode through CSS variables.

### State Management
The application uses TanStack Query (React Query) for server state management, caching, and data synchronization. Local state is managed through React hooks, with custom hooks like `useTimer` and `useWorkout` encapsulating specific business logic. Query client configuration includes optimistic caching strategies to improve performance on mobile devices.

### Mobile-First Design
The architecture prioritizes mobile experience with a maximum width container (max-w-md), touch-friendly interfaces, and responsive design patterns. The layout includes a fixed top bar, scrollable main content area, and bottom navigation, providing a native app-like experience.

### Backend Architecture
The server is built with Express.js and follows a RESTful API design pattern. The application uses a modular route structure with separate handlers for exercises, workout templates, workout sessions, and user progress. Middleware handles request logging, JSON parsing, and error handling uniformly across all endpoints.

### Data Storage Solutions
The application uses Drizzle ORM as the database abstraction layer with PostgreSQL as the target database (configured for Neon serverless). The schema defines core entities including users, exercises, workout templates, workout sessions, and workout sets with proper relationships and constraints. A memory storage implementation provides a fallback for development and testing scenarios.

### Authentication and Authorization
Currently implements a simple demo user system without complex authentication. The architecture is prepared for future authentication implementation with user-scoped data access patterns already established in the API routes.

### Progressive Web App Features
The application includes PWA configuration with a web manifest for installability on mobile devices. Service worker implementation and offline capabilities are prepared through the build configuration, enabling users to access workout data without internet connectivity.

## External Dependencies

### UI Framework Dependencies
- **Radix UI**: Provides headless, accessible UI primitives for components like dialogs, dropdowns, and form controls
- **shadcn/ui**: Component library built on Radix UI with consistent styling and behavior patterns
- **TailwindCSS**: Utility-first CSS framework with custom design tokens and dark mode support
- **Lucide React**: Icon library providing consistent iconography throughout the application

### Data Management
- **TanStack Query**: Server state management library for API data fetching, caching, and synchronization
- **Drizzle ORM**: Type-safe SQL ORM for database operations with PostgreSQL dialect support
- **Drizzle Kit**: Database migration and introspection toolkit for schema management

### Database Infrastructure
- **Neon Database**: Serverless PostgreSQL database platform for production deployment
- **PostgreSQL**: Relational database system supporting complex workout tracking relationships

### Development Tools
- **Vite**: Fast build tool with hot module replacement and optimized production builds
- **TypeScript**: Type safety across the entire application stack
- **ESBuild**: Fast JavaScript bundler for server-side code compilation

### Form and Validation
- **React Hook Form**: Performant form library with minimal re-renders
- **Zod**: Schema validation library for type-safe data validation and transformation

### Routing and Navigation
- **Wouter**: Lightweight routing library optimized for single-page applications

### Utility Libraries
- **date-fns**: Date manipulation and formatting utilities for workout session timestamps
- **clsx & tailwind-merge**: Utility for conditional CSS class composition
- **class-variance-authority**: Type-safe variant API for component styling
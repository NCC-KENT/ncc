# Church Ministry Management System

## Overview

This is a full-stack web application for managing church ministry teams and service schedules. The system allows church members to sign up for different ministry roles (choir and leadership positions) and enables administrators to create and manage worship service schedules with assigned team members.

The application serves the Nepali Covenant Church community, providing a centralized platform for ministry coordination and volunteer management.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript using Vite for build tooling
- **Routing**: Wouter for client-side routing with conditional rendering based on authentication status
- **UI Framework**: Shadcn/ui components built on Radix UI primitives with Tailwind CSS styling
- **State Management**: TanStack React Query for server state management and caching
- **Form Handling**: React Hook Form with Zod validation for type-safe form schemas
- **Styling**: Tailwind CSS with CSS custom properties for theming support

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **API Pattern**: RESTful endpoints with role-based access control
- **Middleware**: Custom logging, JSON parsing, and authentication middleware
- **Error Handling**: Centralized error handling with status code mapping
- **Development**: Vite integration for hot module replacement in development

### Authentication & Authorization
- **Provider**: Replit Auth using OpenID Connect (OIDC) protocol
- **Session Management**: Express sessions with PostgreSQL storage using connect-pg-simple
- **Authorization**: Role-based access with admin/user distinction
- **Security**: Secure cookies, CSRF protection, and session TTL management

### Database Architecture
- **Database**: PostgreSQL with connection pooling via Neon serverless
- **ORM**: Drizzle ORM with type-safe schema definitions
- **Schema Management**: Code-first approach with migration support
- **Key Tables**:
  - `users`: Authentication and profile data with admin flags
  - `members`: Ministry team member information and availability
  - `schedules`: Service schedules with date/time and assignments
  - `sessions`: Secure session storage for authentication

### Data Layer Design
- **Repository Pattern**: Storage interface abstraction for testability
- **Type Safety**: Shared schema types between frontend and backend
- **Validation**: Zod schemas for runtime type checking and form validation
- **Relations**: Drizzle relations for complex queries and data fetching

### Ministry Management Features
- **Member Registration**: Public signup forms for choir and leadership roles
- **Admin Dashboard**: Schedule creation, member management, and status updates
- **Schedule Display**: Public schedule viewing with member assignments
- **Status Tracking**: Member approval workflow (pending -> approved -> inactive)

### Development Architecture
- **Monorepo Structure**: Shared types and schemas between client/server
- **Build Process**: Separate builds for frontend (Vite) and backend (ESBuild)
- **Path Mapping**: TypeScript path aliases for clean imports
- **Hot Reload**: Development server with automatic refresh on changes

## External Dependencies

### Database & Infrastructure
- **Neon Database**: Serverless PostgreSQL hosting with connection pooling
- **WebSocket**: Node.js WebSocket polyfill for Neon serverless connections

### Authentication Services
- **Replit Auth**: OIDC-based authentication service
- **OpenID Client**: OAuth 2.0/OpenID Connect client library
- **Passport.js**: Authentication middleware for Node.js

### UI & Styling Libraries
- **Radix UI**: Headless component primitives for accessibility
- **Tailwind CSS**: Utility-first CSS framework
- **Lucide Icons**: Icon library for consistent iconography
- **Class Variance Authority**: Dynamic class name generation

### Form & Data Management
- **React Hook Form**: Form state management with validation
- **Zod**: Schema validation library for TypeScript
- **TanStack React Query**: Server state management and caching
- **Date-fns**: Date manipulation and formatting utilities

### Development Tools
- **Vite**: Frontend build tool with HMR support
- **ESBuild**: Fast JavaScript bundler for backend
- **TypeScript**: Static type checking across the stack
- **PostCSS**: CSS processing with Tailwind integration

### Replit Integration
- **Replit Plugins**: Development tooling for Replit environment
- **Runtime Error Overlay**: Development error reporting
- **Dev Banner**: Development environment indicators
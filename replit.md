# Sistem Informasi Siswa MTs Yaspika Karangtawang

## Overview

This is a comprehensive student information system built for MTs Yaspika Karangtawang, designed in Indonesian language. The application manages student data, attendance tracking, incident reporting, and generates detailed reports with PDF export capabilities.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

The application follows a modern full-stack architecture with clear separation between client and server components:

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite for fast development and optimized builds
- **UI Framework**: Shadcn/ui components with Radix UI primitives
- **Styling**: Tailwind CSS with custom design tokens
- **State Management**: TanStack React Query for server state
- **Routing**: Wouter for lightweight client-side routing
- **Forms**: React Hook Form with Zod validation

### Backend Architecture
- **Runtime**: Node.js with Express.js REST API
- **Language**: TypeScript with ES modules
- **Database ORM**: Drizzle ORM with PostgreSQL
- **Database Provider**: Neon serverless PostgreSQL
- **API Design**: RESTful endpoints with proper HTTP status codes
- **Validation**: Zod schemas shared between client and server

## Key Components

### Database Schema
The system uses three main entities with proper relationships:
- **Students**: Core student information (ID, nama, kelas, noHp, alamat)
- **Attendance**: Daily attendance tracking with status types (sakit, izin, alpa, kesiangan, bolos)
- **Incidents**: Behavioral incident tracking with predefined categories

### Core Features
1. **Data Siswa**: Complete student management with bulk Excel import/export
2. **Kehadiran**: Attendance tracking with pop-up forms and PDF export
3. **Kejadian**: Incident reporting with categorized violations
4. **Rekap**: Comprehensive reporting with filtering and status calculations

### Status Calculation Logic
- **Attendance Status**: Based on violation counts with color-coded severity
- **Incident Status**: Automated categorization from "Baik" to "Buruk"
- **Reporting**: Real-time aggregation with date range filtering

## Data Flow

1. **Client Requests**: React components use TanStack Query for data fetching
2. **API Layer**: Express routes handle CRUD operations with validation
3. **Database Layer**: Drizzle ORM manages PostgreSQL operations with type safety
4. **Response Processing**: JSON responses with proper error handling
5. **UI Updates**: Optimistic updates with automatic cache invalidation

## External Dependencies

### Core Libraries
- **@neondatabase/serverless**: Serverless PostgreSQL connection
- **drizzle-orm**: Type-safe database operations
- **@tanstack/react-query**: Server state management
- **react-hook-form**: Form handling with validation
- **date-fns**: Date manipulation utilities

### UI Components
- **@radix-ui/***: Accessible component primitives
- **tailwindcss**: Utility-first CSS framework
- **lucide-react**: Icon library
- **jspdf**: PDF generation capabilities
- **xlsx**: Excel file processing

### Development Tools
- **tsx**: TypeScript execution for development
- **esbuild**: Fast JavaScript bundler for production
- **vite**: Development server and build tool

## Deployment Strategy

### Development Environment
- **Dev Server**: Vite dev server with HMR for frontend
- **API Server**: tsx for TypeScript execution with automatic restart
- **Database**: Neon serverless PostgreSQL with connection pooling

### Production Build
- **Frontend**: Static files built with Vite and served by Express
- **Backend**: Bundled with esbuild for optimal performance
- **Database**: Production Neon database with environment variables
- **Deployment**: Single Node.js process serving both API and static files

### Environment Configuration
- **DATABASE_URL**: PostgreSQL connection string (required)
- **NODE_ENV**: Environment mode (development/production)
- **Port Configuration**: Configurable via environment variables

The application is designed for easy deployment on platforms like Replit, with proper environment variable management and database provisioning through Neon's serverless platform.
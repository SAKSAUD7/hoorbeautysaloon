# Hoor Beauty Salon

## Overview

Full-stack production-ready beauty salon website for **Hoor Beauty Salon**. Features a premium luxury frontend with complete public pages, booking system, and a full admin CMS portal.

## Stack

- **Monorepo tool**: pnpm workspaces
- **Node.js version**: 24
- **Package manager**: pnpm
- **TypeScript version**: 5.9
- **Frontend**: React + Vite (artifacts/hoor-beauty), Tailwind CSS, Framer Motion
- **API framework**: Express 5 (artifacts/api-server)
- **Database**: PostgreSQL + Drizzle ORM
- **Validation**: Zod (`zod/v4`), `drizzle-zod`
- **API codegen**: Orval (from OpenAPI spec)
- **Authentication**: JWT (bcryptjs + jsonwebtoken)
- **Build**: esbuild (CJS bundle)

## Pages

### Public
- `/` — Home page with hero, featured services, gallery grid, testimonials, CTA
- `/services` — All services grouped by category (Bridal, Party, Hair, Skincare, Nails, Threading)
- `/gallery` — Masonry gallery with category filters and lightbox
- `/about` — Salon story, founder (Sara Khan), experience
- `/contact` — Contact form, WhatsApp, Instagram
- `/booking` — Full booking form with service selection, date/time picker

### Admin Portal (accessible from footer "Admin Portal" button)
- `/admin/login` — JWT-authenticated admin login
- `/admin` — Dashboard with stats and recent bookings
- `/admin/services` — Full CRUD for services
- `/admin/gallery` — Gallery image management
- `/admin/bookings` — Booking management with status updates
- `/admin/testimonials` — Testimonial CRUD
- `/admin/content` — CMS editor for all site content

## Admin Credentials
- **Email**: admin@hoorbeauty.com
- **Password**: admin123

## Key Commands

- `pnpm run typecheck` — full typecheck across all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks from OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- `pnpm --filter @workspace/api-server run dev` — run API server locally
- `pnpm --filter @workspace/hoor-beauty run dev` — run frontend locally

## API Routes

- `GET /api/services` — List services (public)
- `POST /api/services` — Create service (auth required)
- `PUT /api/services/:id` — Update service (auth required)
- `DELETE /api/services/:id` — Delete service (auth required)
- `GET /api/gallery` — List gallery images (public, supports ?category=)
- `GET /api/bookings` — List bookings (auth required)
- `POST /api/bookings` — Create booking (public)
- `PUT /api/bookings/:id` — Update booking status (auth required)
- `GET /api/testimonials` — List testimonials (public)
- `GET /api/content` — Get CMS content (public)
- `PUT /api/content` — Update CMS content (auth required)
- `POST /api/auth/login` — Admin login
- `GET /api/dashboard/stats` — Admin dashboard stats (auth required)

## Design

- Colors: Blush pink, nude beige, warm ivory, deep rose, gold accents
- Fonts: Playfair Display (headings), Poppins (body)
- Animations: Framer Motion scroll reveals
- Features: WhatsApp floating button, sticky navbar, mobile-first responsive

## Database Schema

Tables: `admins`, `services`, `gallery`, `bookings`, `testimonials`, `site_content`

# NextJS Finance Application

## Project Overview
A modern full-stack finance application built with the "bleeding-edge" stack:
- **Next.js** - React framework with App Router
- **Tailwind CSS** - Utility-first styling
- **PostgreSQL** - Robust relational database
- **TypeScript** - Type safety throughout the stack

## Tech Stack Details

### Frontend
- Next.js 14+ with App Router (app directory)
- React 18+ with Server Components
- Tailwind CSS for styling
- TypeScript for type safety

### Backend
- Next.js API Routes (Route Handlers)
- PostgreSQL database
- ORM: Prisma (recommended) or Drizzle

### Development Philosophy
- Prioritize type safety - use TypeScript strictly
- Leverage Server Components by default
- Use Tailwind utility classes, avoid custom CSS when possible
- Follow Next.js conventions for file-based routing

## Project Structure (Planned)
```
├── app/                    # Next.js App Router
│   ├── api/               # API routes
│   ├── dashboard/         # Dashboard pages
│   └── layout.tsx         # Root layout
├── components/            # Reusable components
│   ├── ui/               # Base UI components
│   └── features/         # Feature-specific components
├── lib/                  # Utility functions
├── prisma/               # Database schema and migrations
└── public/               # Static assets
```

## Development Guidelines

### Code Style
- Use TypeScript strict mode
- Prefer Server Components over Client Components
- Keep components small and focused
- Use Tailwind classes for styling
- Follow Next.js naming conventions

### Database
- Use migrations for schema changes
- Always validate inputs before database operations
- Use transactions for multi-step operations
- Consider performance for large datasets

### Security (Critical for Finance Apps)
- Never expose database credentials
- Validate and sanitize all user inputs
- Use parameterized queries (ORM handles this)
- Implement proper authentication and authorization
- Log sensitive operations appropriately
- Use HTTPS in production
- Consider rate limiting for API routes

### Testing
- Write unit tests for business logic
- Test database operations with test database
- Consider E2E tests for critical user flows

## Common Commands

```bash
# Development
npm run dev

# Build
npm run build

# Database migrations (if using Prisma)
npx prisma migrate dev
npx prisma generate

# Type checking
npx tsc --noEmit
```

## Finance-Specific Considerations
- Always use decimal types for monetary values (never float)
- Handle currency formatting correctly
- Implement proper error handling for financial operations
- Consider audit trails for sensitive operations
- Validate amounts are positive where appropriate
- Handle edge cases (division by zero, negative values, etc.)
# Decision Record: Use Next.js as the Framework

## Status

Accepted

## Context

We need to build a personal website that serves as a code-based CV. The site needs to be fast, SEO-friendly, and support interactive features like an AI chat. We want a framework that provides a good developer experience while keeping the tech stack simple and practical.

## Decision

We will use Next.js 16 as the web framework for this project.

## Rationale

- **Simplicity**: Next.js provides a complete solution out of the box—routing, SSR, API routes, and deployment optimization
- **Best tool for the job**: For a personal website that needs to be fast and SEO-friendly, Next.js is a practical choice
- **Mature ecosystem**: Well-established framework with large community, extensive documentation, and proven patterns
- **Developer experience**: Excellent tooling, hot reload, and clear conventions
- **Hosting integration**: Works seamlessly with Vercel (our chosen hosting platform)
- **No unnecessary complexity**: We're not trying to flex with tech choices—just picking what works best for this use case

## Alternatives Considered

- **TanStack Start**: Modern React framework with excellent TypeScript support and flexible rendering
  - Rejected: Newer framework with smaller ecosystem and community; Next.js is more established and has better Vercel integration
- **React with Vite (SPA)**: Client-side React application with fast build tooling
  - Rejected: Less optimal for SEO and initial load performance; would require additional setup for SSR/SSG if needed later

## Consequences

- **Positive**:
  - Fast development with built-in optimizations
  - Great SEO out of the box with SSR/SSG
  - Easy deployment to Vercel
  - Large ecosystem and community support
  - Built-in API routes for backend functionality
- **Negative/Trade-offs**:
  - Adds some framework overhead (but minimal for our use case)
  - Learning curve if unfamiliar (but widely known)

## Notes

- Next.js provides everything we need without requiring additional build tools or configuration
- The App Router will be used for modern routing patterns
- API routes will handle AI chat and other backend functionality
- Next.js 16 introduces cache components and partial pre-rendering—this project will be an opportunity to discover and evaluate these new features

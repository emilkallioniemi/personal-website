# Decision Record: Host on Vercel

## Status

Accepted

## Context

We need to host a Next.js application that will serve as a personal website. The hosting solution should be simple, reliable, and require minimal configuration. Since we're using Next.js, we want a platform that integrates seamlessly.

## Decision

We will host the website on Vercel.

## Rationale

- **Simplicity**: Zero-config deployment for Next.js applications
- **Best tool for the job**: Vercel is built by the Next.js team, providing optimal integration
- **No unnecessary complexity**: We're choosing the most straightforward option, not trying to demonstrate knowledge of complex infrastructure
- **Free tier**: Sufficient for a personal website
- **Automatic deployments**: Git-based deployments with preview URLs
- **Global CDN**: Fast performance worldwide out of the box
- **No special requirements**: We don't have specific requirements around EU data residency or other regional constraints, so Vercel's default setup works perfectly

## Consequences

- **Positive**:
  - Instant deployments from Git
  - Automatic HTTPS and CDN
  - Preview deployments for PRs
  - Zero server maintenance
  - Excellent Next.js optimization
- **Negative/Trade-offs**:
  - Vendor lock-in (but acceptable for a personal site)
  - Free tier limits (but sufficient for our needs)

## Notes

- Vercel provides the simplest path from code to production
- No need to configure servers, SSL, or CDN—all handled automatically
- Perfect alignment with our "simplicity" theme

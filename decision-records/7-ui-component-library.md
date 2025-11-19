# Decision Record: Use shadcn/ui as the UI Component Library

## Status

Accepted

## Context

We need a UI component library for building the personal website interface. We want components that are:

- Accessible by default
- Customizable and themeable
- Built on solid foundations
- Easy to integrate with Next.js and Tailwind CSS
- Type-safe with TypeScript

## Decision

We will use shadcn/ui as the UI component library for this project.

## Rationale

- **You own the code**: This is the biggest advantage—shadcn/ui isn't a traditional library dependency. Components are copied directly into your codebase, meaning you have full ownership and control. You can modify, extend, or customize any component without being constrained by external package limitations or waiting for upstream updates.
- **Built on Radix UI**: Provides excellent accessibility out of the box with proper ARIA attributes and keyboard navigation
- **Tailwind CSS integration**: Seamlessly works with our existing Tailwind setup and allows for easy customization
- **TypeScript support**: Full type safety with TypeScript
- **Next.js compatibility**: Designed specifically for React and Next.js with RSC (React Server Components) support
- **Comprehensive component set**: Includes all common UI patterns (forms, dialogs, navigation, data display, etc.)
- **Active maintenance**: Well-maintained with regular updates and a large community

## Alternatives Considered

No alternatives were seriously evaluated. shadcn/ui is the best way to get started quickly with high quality components, so the decision was straightforward.

## Consequences

- **Positive**:
  - **You own the code**: Components are part of your codebase, not external dependencies—full ownership and control
  - Fast development with pre-built, accessible components
  - Can modify any component directly without constraints from external packages
  - Consistent design system with the "new-york" style variant
  - Easy theming with CSS variables and Tailwind
  - No external runtime dependencies for UI components (just Radix UI primitives)
- **Negative/Trade-offs**:
  - Need to manually update components if we want to pull in upstream changes
  - Initial setup requires installing many Radix UI packages as dependencies

## Notes

- Using the "new-york" style variant for a more refined, modern aesthetic
- Components are configured with TypeScript and RSC support
- Path aliases are set up for easy imports (`@/components`, `@/lib/utils`, `@/hooks`)
- The `cn()` utility function (from `lib/utils.ts`) combines `clsx` and `tailwind-merge` for conditional class names
- Icon library is set to Lucide React for consistent iconography
- Base color is zinc for a neutral, professional look
- CSS variables are enabled for theming support

# Decision Record: Use OpenAI as LLM Provider

## Status

Accepted

## Context

The website needs an AI chat feature that allows visitors to have natural conversations about my background, projects, and interests. This requires a language model that can understand context and provide helpful, conversational responses.

## Decision

We will use OpenAI as the LLM provider, accessed through the "ai" npm package (Vercel AI SDK) rather than OpenAI's SDK directly.

## Rationale

- **Simplicity**: OpenAI provides a straightforward API for conversational AI
- **Best tool for the job**: OpenAI's models are well-suited for conversational AI
- **Quality**: OpenAI provides high-quality models that deliver good user experience
- **Abstraction layer**: The "ai" npm package provides a popular, widely-adopted abstraction that makes it easy to switch providers if needed (though we'll stick with OpenAI)
- **UI utilities**: The "ai" package provides nice UI components and utilities that simplify building chat interfaces
- **No unnecessary complexity**: We're not trying to demonstrate multi-provider architecture—just picking what works

## Consequences

- **Positive**:
  - Simple integration with the "ai" package
  - Good documentation and community support (both OpenAI and the "ai" package)
  - High-quality conversational responses
  - Built-in UI components and utilities from the "ai" package
  - Provider abstraction allows flexibility if needed in the future
- **Negative/Trade-offs**:
  - API costs (but reasonable for a personal site)
  - Vendor dependency (but acceptable for this use case)
- **Risks and Mitigations**:
  - Risk: API costs
    - Mitigation: Monitor usage, implement rate limiting if needed

## Notes

- We'll use the latest appropriate OpenAI model for the chat interface (as of November 2025, GPT-5 is available and would be the primary choice)
- Implementation will use the "ai" npm package (Vercel AI SDK) as an abstraction layer, with OpenAI as the provider
- The chat will be enhanced with context from a knowledge base (see separate decision record for vector database approach)

# Decision Record: Use ElevenLabs for Voice Cloning

## Status

Accepted

## Context

The website includes an optional voice cloning feature where visitors can have voice-to-voice conversations with an AI version of me. This requires high-quality text-to-speech and voice cloning capabilities.

## Decision

We will use ElevenLabs for voice cloning and text-to-speech functionality.

## Rationale

- **Simplicity**: ElevenLabs provides a straightforward API for voice cloning
- **Best tool for the job**: Known for high-quality voice synthesis and cloning
- **Quality**: Produces natural-sounding voice output
- **Ease of integration**: Well-documented API
- **No unnecessary complexity**: We're choosing the most practical option for voice features

## Consequences

- **Positive**:
  - High-quality voice output
  - Simple API integration
  - Good documentation
  - Reliable service
- **Negative/Trade-offs**:
  - Additional API costs (separate from OpenAI)
  - Another vendor dependency
  - Voice cloning requires initial voice sample recording
  - Once my voice is cloned, it's out there and can't really be undone—anyone could potentially use my voice (but that's part of the fun!)
- **Risks and Mitigations**:
  - Risk: API costs
    - Mitigation: Monitor usage, implement rate limiting if needed

## Notes

- This is an optional/exploratory feature (as noted in the README)
- Voice cloning will require recording voice samples to train the model
- The feature can be disabled if it doesn't meet quality standards or becomes too costly

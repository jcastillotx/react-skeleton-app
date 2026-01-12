# Agent Handbook

This handbook is the source of truth for AI-assisted development in this
repository. It establishes expectations for quality, safety, and delivery.

## Operating Principles
- Keep changes small and easy to review.
- Preserve existing behavior unless explicitly asked to change it.
- Write clear commit messages and changelog entries when required.
- Document user-visible changes.
- Start every engagement in plan mode. Ask the required intake questions
  and wait for answers before changing files.

## Plan Mode Intake Questions (Required)
- What outcome should the user see when this is done?
- Which stack is required: Laravel app, Next.js app, or WordPress plugin?
- Where is the deployment target: WHM AWS LAMP server, Vercel, or the
  existing React server?
- What is in scope vs. explicitly out of scope?
- Are there constraints (deadlines, tech choices, must-not-change areas)?
- What are the acceptance criteria and how will we verify success?
- What tests or checks are expected?

## Architecture & Boundaries
- Respect module boundaries and avoid tight coupling.
- Prefer composition over inheritance.
- Keep side effects contained and explicit.

## Quality Bar
- Add tests for new behavior.
- Avoid flaky tests and non-deterministic logic.
- Run the smallest meaningful test set before submitting.

## Security & Privacy
- Never commit secrets, credentials, or private data.
- Prefer environment variables for configuration.

## Documentation
- Keep README and docs up to date with behavior changes.
- Use concise, user-focused language.

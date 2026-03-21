# Research

**Decisions:**
- Use existing `MohammedApps` layout, focusing solely on the React logic for Exam Builder.
- Exclude `exambuilder` index.html completely from the new build process, or strip out all components not related to taking exams.

**Rationale:** The existing Music Academy UI contains many extraneous scripts, API methods, and features that inflate bundle size and distract from the primary generative AI Exam Builder interface.

**Alternatives Considered:** Trying to refactor the monolithic HTML into features. However, isolating at the deployment level is much safer and easier to maintain.

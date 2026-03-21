# Implementation Plan: Isolate Exam Builder

**Branch**: `001-isolate-exam-builder` | **Date**: 2026-03-21 | **Spec**: [spec.md](./spec.md)
**Input**: Feature specification from `/specs/001-isolate-exam-builder/spec.md`

## Summary

The goal is to cleanly decouple the standalone Exam Builder from all Music Academy dependencies and UI components, ensuring it can be built, executed, and maintained as a standalone application.

## Technical Context

**Language/Version**: TypeScript, HTML/CSS (ESM)
**Primary Dependencies**: React (Vite-based build), Google GenAI, Tailwind CSS
**Storage**: N/A (Stateless / in-memory / local storage)
**Testing**: Vitest / Playwright (if applicable)
**Target Platform**: Web Browser
**Project Type**: Single Page Application (SPA)
**Performance Goals**: <2s time to interactive
**Constraints**: Purely frontend AI integration, offline-capable where possible
**Scale/Scope**: Solo/class-level execution, tens of concurrent exams

## Constitution Check

*GATE: Passed. Feature relies on existing framework tools (React/Vite) without introducing unnecessary architectural overhead.*

## Project Structure

### Documentation (this feature)

```text
specs/001-isolate-exam-builder/
├── plan.md              # This file
├── research.md          # Technology decisions
├── data-model.md        # Core entities description
├── quickstart.md        # Launch instructions
└── contracts/           # API interfaces (N/A for SPA)
```

### Source Code (repository root)

```text
src/
├── components/          # React components solely for the Exam Builder
├── services/            # geminiService.ts and related logic
├── types.ts             # Shared interfaces (Question, ExamResult, etc.)
└── locales.ts           # i18n translations
index.html               # Main entry point (Music Academy Nav Removed)
```

**Structure Decision**: Option 1 (Single project frontend SPA).

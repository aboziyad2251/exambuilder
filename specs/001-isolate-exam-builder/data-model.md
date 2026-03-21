# Data Model

The Exam Builder relies purely on frontend, transient state with the following principal entities:

## Entities

- **Question**
    - Fields: `id`, `text`, `type`, `options[]`, `correctAnswer`, `difficulty`, `topic`
- **ExamResult**
    - Fields: `scorePercentage`, `correctCount`, `incorrectCount`, `answers{}`
- **StudentInfo**
    - Fields: `name`, `level`
- **ExamMetadata**
    - Fields: `courseName`, `topics[]`, `concepts[]`

There are no persistent database schemas required for the standalone builder functionality at this stage. All processing is handed off to the Gemini AI models (`geminiService.ts`).

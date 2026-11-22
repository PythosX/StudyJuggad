# StudyJugaad AI

Premium dark-first hackathon MVP for turning study material into structured learning and exam practice.

## What is included

- Responsive landing page with product preview and motion-safe interactions
- Demo login and registration (local browser only)
- Four-step B.Tech onboarding with curriculum, multi-select subjects, and custom subjects
- Dashboard with subject cards, quick actions, activity feed, and 20/45/90-minute revision plans
- Subject workspaces with PDF/TXT/DOCX validation, upload progress/extraction state, delete, search, and subject isolation
- Concept Tutor with Midsem/Endsem, three learning levels, structured lesson output, copy action, and honest source messaging
- Paper Studio with Midsem, Endsem, and Custom Question Paper configurations, validated generated marks, answer-key action, and print preview
- Settings, motion preference, local data management, keyboard focus styles, and reduced-motion CSS
- Dockerfile, `.env.example`, and `.gitignore`

The current MVP intentionally uses deterministic demo responses. It does not claim that generated questions predict a real examination and it does not fabricate uploaded-file citations.

## Run locally

Requires Node.js only for the syntax check and Python 3 for the static server.

```bash
npm test
npm start
```

Then open http://localhost:4173.

Alternatively:

```bash
python -m http.server 4173
```

## Demo access

Click **Start My Jugaad** and use any valid email with a password of at least six characters. The demo stores state in `localStorage`; no credentials are sent anywhere.

## Docker

```bash
docker build -t studyjugaad-ai .
docker run --rm -p 8080:80 studyjugaad-ai
```

Open http://localhost:8080.

## Next production steps

1. Replace localStorage with authenticated server-side persistence and per-user storage.
2. Add a FastAPI upload/extraction service for PDF, DOCX, and OCR where required.
3. Add a provider adapter that reads the documented environment variables in `.env.example`; keep keys server-side.
4. Add deterministic unit and browser tests for upload extraction, marks totals, source retrieval, timeout/rate-limit errors, and accessibility journeys.

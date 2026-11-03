# Distributed Job Scheduler

A production-inspired platform for reliably executing asynchronous background jobs across multiple workers — REST API, atomic job claiming, configurable retry backoff (fixed/linear/exponential), dead-letter handling, worker heartbeats, and a live-updating dashboard.

## Project structure

```
distributed-job-scheduler/
├── backend/          Express + TypeScript API, Prisma/PostgreSQL, standalone worker process
├── frontend/          React + TypeScript dashboard (Vite)
├── docs/              API docs, architecture + ER diagram, design decisions
└── README.md          you are here
```

## Prerequisites

- Node.js 18+
- PostgreSQL 16 (via Docker or a local install)
- npm

## Setup

### 1. Database

```bash
docker run --name jobsched-pg -e POSTGRES_PASSWORD=postgres -e POSTGRES_DB=jobscheduler -p 5432:5432 -d postgres:16
```
(Or point `DATABASE_URL` in `backend/.env` at any Postgres instance you already have.)

### 2. Backend

```bash
cd backend
npm install
copy .env.example .env
npx prisma migrate dev
npm run dev
```
API runs on `http://localhost:5000`.

### 3. Worker

In a separate terminal — run as many of these as you want to see concurrent job claiming in action:
```bash
cd backend
npm run worker
```
Each invocation registers as an independent worker process that polls the database, atomically claims the next eligible job, executes it, and writes its result to execution history.

### 4. Frontend

```bash
cd frontend
npm install
copy .env.example .env
npm run dev
```
Dashboard runs on `http://localhost:5173`.

### 5. Try it

1. Register an account at `http://localhost:5173/register`.
2. Create a project and a queue via the Queues page.
3. Create a job via the API (see `docs/API.md` for the exact request):
   ```bash
   curl -X POST http://localhost:5000/api/jobs -H "Authorization: Bearer YOUR_TOKEN" -H "Content-Type: application/json" -d "{\"name\":\"my-job\",\"queueId\":\"YOUR_QUEUE_ID\",\"payload\":{}}"
   ```
4. Watch it move through the lifecycle on the Job Explorer page, and watch the worker terminal log the claim.
5. Run a second `npm run worker` in another terminal and submit several jobs at once — you'll see them split between the two workers with no job ever claimed twice.

## Documentation

- [`docs/API.md`](docs/API.md) — every REST endpoint, request/response shapes
- [`docs/architecture.md`](docs/architecture.md) — system architecture + ER diagram (Mermaid — paste into mermaid.live to export as PNG)
- [`docs/project-report.md`](docs/project-report.md) — design decisions, trade-offs, and known limitations

## Testing

```bash
cd backend
npm test
```
Covers retry backoff calculation (fixed/linear/exponential) and the dead-letter-queue transition condition.

## Known limitations

See `docs/project-report.md` for the full, honest list — most notably: no automatic reclaim of jobs left behind by an ungracefully-crashed worker (only clean shutdown is handled), no idempotency keys on job creation, and queue-level pause/resume/priority configuration isn't wired up end-to-end yet.

# openclaw-model-orchestrator -- Next Actions

## T-001: Integration test api.inference [HIGH] [ready]
- Install plugin locally
- Test `/orchestrate help` output
- Test `/orchestrate models` fetches real model list
- Test `/orchestrate recommend "Build REST API"` returns classification
- Test a simple fan-out with 2 workers
- Validate api.inference response shape

## T-002: GitHub repo + push [HIGH] [ready]
- Create elvatis/openclaw-model-orchestrator on GitHub
- Push initial commit
- Set up branch protection

## T-003: Timeout + error recovery [MEDIUM] [blocked by T-001]
- Add configurable timeout per worker (default 60s)
- Graceful degradation: if 1 worker fails, continue with others
- Retry logic for transient errors (429, 503)
- Report partial results if not all workers complete

## T-004: Progress reporting [MEDIUM] [blocked by T-001]
- Send intermediate messages during long orchestrations
- "Planning phase complete, starting 3 workers..."
- "Worker 2/3 complete..."
- Use message tool to update chat in real-time

## T-005: Publish npm + ClawHub [LOW] [blocked by T-001, T-002]
- npm publish --access public
- clawhub publish
- Update MODELS.md with orchestrator references

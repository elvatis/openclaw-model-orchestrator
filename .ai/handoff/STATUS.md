# openclaw-model-orchestrator -- Status

## Current State
- **Version:** 0.1.0 (scaffold)
- **Phase:** Initial implementation
- **Health:** Untested

## Architecture
- Single TypeScript file plugin (index.ts)
- Registers `/orchestrate` command with subcommands
- Model discovery via `openclaw models list` CLI
- Task classification via keyword matching
- AAHP v3 handoff objects for inter-model communication
- 3 orchestration modes: fan-out, pipeline, consensus
- 5 predefined task profiles: coding, research, security, review, bulk

## Dependencies
- OpenClaw Gateway (host plugin)
- `api.inference()` for model calls (needs validation)
- `openclaw` CLI for model discovery

## Open Questions
- Does `api.inference()` accept alias names or only full model IDs?
- What is the response shape of `api.inference()`?
- Rate limiting behavior when hitting multiple models in parallel?

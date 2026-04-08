# cf_ai_deploycoach

An AI-powered deployment debugging assistant built on Cloudflare Agents.

## What it does
DeployCoach helps engineers diagnose and fix deployment failures in 
containerized and distributed systems. Paste a Kubernetes error, Docker 
log, or Jenkins failure and it identifies the root cause, explains it, 
and gives actionable fixes — remembering your full conversation history.

## Components
- **LLM**: Kimi K2.5 via Cloudflare Workers AI
- **Memory/State**: Durable Objects with built-in SQL (conversation persistence)
- **Workflow**: Cloudflare Agents SDK with AIChatAgent
- **User Input**: Streaming chat UI via WebSockets

## Try it live
https://cf-ai-deploycoach.manyajainrkm.workers.dev

## Run locally
git clone https://github.com/ManyaJainrkm/cf_ai_deploycoach
cd cf_ai_deploycoach
npm install
npm run dev
Open http://localhost:5173
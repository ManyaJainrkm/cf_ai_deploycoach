# cf_ai_deploycoach

An AI-powered deployment debugging assistant built on Cloudflare Agents.

## Why this exists
DeployCoach was built from 9 months of real deployment work on the UPYOG 
Smart Cities platform at the National Institute of Urban Affairs, Government 
of India. The error patterns in this tool — CrashLoopBackOff, Bitnami 
permission failures, Jenkins JAVA_HOME errors, Kubernetes ingress version 
conflicts — are errors that were debugged, documented, and resolved firsthand 
on a live government platform serving cities across India.

## What it does
Paste a Kubernetes error, Docker log, or Jenkins failure into the chat. 
DeployCoach identifies the error type using pattern matching, explains the 
root cause, and gives you specific commands or config fixes to resolve it. 
It remembers your full conversation history so you can debug iteratively 
without re-explaining context.

## Components
- **LLM**: Kimi K2.5 via Cloudflare Workers AI (Workers AI hosted model)
- **Memory/State**: Durable Objects with built-in SQL — conversation persists 
  across sessions
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

## Error patterns supported
CrashLoopBackOff, OOMKilled, ImagePullBackOff, Bitnami permission errors, 
Jenkins JAVA_HOME failures, Jenkins BUILD FAILURE, Kubernetes ingress version 
conflicts, missing secrets/configmaps, connection refused, panic exit status
# Inntris Core

> **Protecting Intellect. The Universal Liability Shield for Autonomous Agents.**

Inntris INC provides advanced security infrastructure and defensive protocols for artificial intelligence systems and third-party platforms. We serve as a protective shell that safeguards high-level cognitive models and ensures their integrity across diverse digital ecosystems.

## The Universal Trust Layer for AI Agents

Inntris Core is a production-ready **Verification & Liability Platform** for AI Agents. Think of it as the **"VISA Network" for AI** — providing Identity, Audit, and Control for any AI agent through a standardized Model Context Protocol (MCP) Server.

### Core Philosophy

- **"Fail Closed"** — If an agent cannot be verified, it cannot act
- **"Zero Trust"** — Never trust the client; always verify the signature
- **"Forensic Grade"** — Audit logs are not for debugging; they are for court

---

## Architecture Overview

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                           AI AGENT (Lovable/Replit/LangChain)               │
│                                      │                                      │
│                          ┌───────────▼───────────┐                          │
│                          │   MCP Server (Inntris)│                          │
│                          │   "Universal Adapter" │                          │
│                          └───────────┬───────────┘                          │
└──────────────────────────────────────┼──────────────────────────────────────┘
                                       │
                    ┌──────────────────▼──────────────────┐
                    │        Core Enforcer API            │
                    │        "The Central Bank"           │
                    │  ┌─────────────────────────────┐   │
                    │  │ Identity Service (Ed25519)  │   │
                    │  │ Policy Engine (Limits)      │   │
                    │  │ Trust Scorer (0-100)        │   │
                    │  └─────────────────────────────┘   │
                    └──────────────────┬──────────────────┘
                                       │
        ┌──────────────────────────────┼──────────────────────────────┐
        │                              │                              │
        ▼                              ▼                              ▼
┌───────────────┐           ┌───────────────────┐           ┌───────────────┐
│   PostgreSQL  │           │   Anchor Worker   │           │  Trust Badge  │
│  (Supabase)   │           │ "Forensic Recorder"│          │   (React)     │
│  + TimescaleDB│           │  Merkle → Base L2 │           │ "Verified UI" │
└───────────────┘           └───────────────────┘           └───────────────┘
                                                                    │
                                       ┌────────────────────────────┘
                                       ▼
                    ┌──────────────────────────────────────┐
                    │       Frontend Dashboard             │
                    │       "Management Console"           │
                    │  ┌────────────┬────────────────────┐ │
                    │  │Admin Console│   Agent Portal    │ │
                    │  │Audit Explorer│ Public Verify    │ │
                    │  └────────────┴────────────────────┘ │
                    └──────────────────────────────────────┘
```

---

## Components

### Component A: MCP Server (`mcp_server/`)

The **"Universal Adapter"** that runs alongside any AI agent.

- Exposes `inntris_guard` tool via Model Context Protocol
- Intercepts critical actions before execution
- Signs requests with Ed25519 private key
- Returns APPROVED (with token) or BLOCKED (raises exception)

### Component B: Core Enforcer API (`api/`)

The **"Central Bank"** for agent verification.

- **Identity Service**: Validates Ed25519 signatures against registered public keys
- **Policy Engine**: Enforces limits (daily caps, per-action limits, rate limiting)
- **Trust Scorer**: Real-time trust scores (0-100) based on agent behavior

### Component C: Audit Engine (`workers/`)

The **"Forensic Recorder"** for immutable audit trails.

- Ingests all verification events into PostgreSQL
- Batches logs into Merkle trees every hour
- Anchors Merkle roots to Base L2 blockchain
- Provides cryptographic proof of audit existence

### Component D: Trust Badge (`trust_widget/`)

The **"Embeddable Widget"** for end-user verification.

- Lightweight React component
- Displays verified status and trust score
- Queries public API endpoint
- Real-time refresh capability

### Component E: Frontend Dashboard (`frontend/`)

The **"Management Console"** for organizations and developers.

- **Admin Console**: Organization management, agent policies, security alerts, API keys
- **Agent Portal**: Developer dashboard, credentials, verification playground
- **Audit Explorer**: Log search, Merkle proof verification, compliance exports
- **Public Verification**: Public agent trust verification page

---

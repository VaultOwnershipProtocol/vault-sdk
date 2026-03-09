# vault-sdk
Developer SDK for connecting AI agents to Vault context.
# Vault Context Protocol

The open protocol for permissioned personal AI context.

Vault Context Protocol defines how AI systems can securely request, verify, and use personal context owned and controlled by individuals.

It introduces the **ownership layer for AI**.

---

## Overview

Artificial intelligence systems are becoming more powerful every day.

But they still lack one critical capability:

**personal context.**

AI tools do not know:

- who you are  
- what you care about  
- what you are working on  
- your preferences  
- your knowledge  
- your goals  

As a result, users constantly repeat themselves across AI systems.

The Vault Context Protocol introduces a standardized way for AI systems to request and use **user-owned context** with explicit permission.

Vault provides a **secure interface between humans and AI systems**.

---

## The Ownership Layer

AI systems provide intelligence.

Vault provides ownership and context.


Human
↓
Vault
↓
AI Tools & Agents
↓
AI Models


Humans generate the data and context that make AI useful.

Vault ensures individuals retain control over that context.

---

## Core Principles

The Vault Context Protocol is designed around five principles.

### 1. User Ownership

Users own the data and context that power their AI experiences.

Vault ensures individuals can:

- view their data  
- control access  
- revoke permissions  
- delete context  

---

### 2. Explicit Permission

AI systems must request permission before accessing personal context.

Nothing is shared without user approval.

---

### 3. Interoperability

Users should be able to move between AI systems without losing their personal context.

The Vault protocol allows AI tools to interoperate through a shared context standard.

---

### 4. Transparency

Users should always know:

- what data is being accessed  
- which systems accessed it  
- when it was used  

---

### 5. Portability

Personal context should move with the user across platforms and AI systems.

---

## Core Concepts

The Vault Context Protocol introduces three core primitives.

### Context Blocks

Structured units of personal context.

Examples include:

- identity  
- preferences  
- projects  
- knowledge  
- documents  
- goals  

Example structure:

```json
{
  "identity": {
    "name": "Byron",
    "role": "Founder"
  },
  "preferences": {
    "tone": "structured",
    "format": "concise"
  },
  "projects": [
    "Vault AI",
    "Ownership Layer Manifesto"
  ]
}

Context blocks allow AI systems to understand users quickly.

Permission Requests

AI systems must request permission before accessing context.

Example request:

ChatGPT is requesting access to:

• Preferences  
• Projects  
• Knowledge  

Approve?

Users can approve or deny access.

Vault Passport

When permission is granted, Vault issues a Vault Passport.

A Vault Passport is a signed credential allowing an AI system to access specific context blocks.

Example structure:

{
  "vault_id": "user_123",
  "scopes": ["preferences", "projects"],
  "issued_at": "2026-01-01",
  "expires_at": "2026-01-02",
  "signature": "vault_signature_hash"
}

Passports are:

scoped

time-limited

revocable

verifiable

Developer Flow

Example interaction between an AI agent and a Vault.

Agent → Request context  
Vault → Ask user for permission  
User → Approve request  
Vault → Issue Vault Passport  
Agent → Receive structured context

Developers interact with Vault through SDKs and APIs.

Example:

from vault import connect_vault

vault = connect_vault(user_id="123")

context = vault.get_context(["preferences", "projects"])
Example Use Cases

Vault enables developers to build AI systems that understand users instantly.

Example applications include:

AI personal assistants

AI research copilots

AI travel planners

AI personal CRMs

AI planning agents

AI knowledge assistants

All powered by user-owned context.

Relationship to AI Systems

Vault does not replace AI models.

Instead, Vault provides the context layer that allows AI systems to operate effectively.

AI models provide intelligence.

Vault provides identity and context.

Together they create personal AI.

Protocol Status

Vault Context Protocol is currently in early development.

This repository defines the initial specification and core primitives.

Future work includes:

protocol extensions

SDK implementations

developer tooling

ecosystem integrations

Contributing

We welcome discussion and contributions from developers, researchers, and AI builders.

You can contribute by:

proposing protocol improvements

suggesting use cases

building integrations

creating SDKs

Please open an issue or start a discussion.

License

MIT License

Copyright 2026 Byron Goodman

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the “Software”), to deal
in the Software without restriction.

See LICENSE file for full details.

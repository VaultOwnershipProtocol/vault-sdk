# vault-sdk
Developer SDK for connecting AI agents to Vault context.
# Vault SDK

Developer SDK for connecting AI agents and applications to Vault context.

Vault SDK allows developers to request, verify, and use permissioned personal context through the Vault Context Protocol.

Vault introduces the **ownership layer for AI**.

---

## Overview

AI systems are powerful, but they still lack one critical ingredient:

**personal context**

Most AI applications start from zero.

They do not know:

- who the user is
- what the user is working on
- the user's preferences
- the user's goals
- the user's knowledge

Vault SDK makes it easy for developers to give AI systems secure access to user-owned context with explicit permission.

---

## What the SDK Does

Vault SDK provides a simple interface for:

- connecting a user vault
- requesting context
- verifying a Vault Passport
- retrieving approved context blocks
- revoking access

The goal is simple:

**AI agents should never start from zero again.**

---

## Core Concepts

### User Vault

A secure personal context store owned and controlled by the user.

A vault may contain:

- identity
- preferences
- projects
- knowledge
- documents
- goals

---

### Vault Passport

A signed, scoped, time-limited credential issued by Vault after the user approves access.

Passports are:

- scoped
- verifiable
- revocable
- time-bound

---

### Context Blocks

Structured units of personal context that AI systems can request.

Examples:

- preferences
- projects
- knowledge
- goals

---

## Installation

### Python

```bash
pip install vault-ai
TypeScript
npm install vault-ai
Quickstart
Python
from vault_ai import connect_vault, verify_passport

vault = connect_vault(user_id="user_123")

passport = vault.request_passport(
    agent_id="research-agent",
    scopes=["preferences", "projects"],
    purpose="Provide personalized research support"
)

is_valid = verify_passport(passport)

if is_valid:
    context = vault.get_context(passport)
    print(context)
TypeScript
import { connectVault, verifyPassport } from "vault-ai";

const vault = await connectVault({ userId: "user_123" });

const passport = await vault.requestPassport({
  agentId: "research-agent",
  scopes: ["preferences", "projects"],
  purpose: "Provide personalized research support",
});

const isValid = await verifyPassport(passport);

if (isValid) {
  const context = await vault.getContext(passport);
  console.log(context);
}
Example Developer Flow
User connects Vault
      ↓
App requests context scopes
      ↓
Vault asks user for permission
      ↓
Vault issues Passport
      ↓
App verifies Passport
      ↓
App receives approved context
Example Use Cases

Vault SDK can be used to build:

AI personal assistants

AI research copilots

AI planning tools

AI travel planners

AI personal CRMs

AI knowledge systems

All powered by user-owned context.

Proposed API

The initial SDK surface is designed to stay simple.

Python
connect_vault(user_id: str)
request_passport(agent_id: str, scopes: list[str], purpose: str)
verify_passport(passport: dict)
get_context(passport: dict)
revoke_access(passport_id: str)
TypeScript
connectVault({ userId: string })
requestPassport({ agentId: string, scopes: string[], purpose: string })
verifyPassport(passport: object)
getContext(passport: object)
revokeAccess(passportId: string)
Relationship to Vault Context Protocol

Vault SDK is the developer interface for applications using the Vault Context Protocol.

The protocol defines:

how context is structured

how permissions are requested

how passports are issued

how access is verified

The SDK makes it easy to use those primitives in real products.

Status

Vault SDK is currently in early development.

Planned work includes:

Python package

TypeScript package

example integrations

local development tooling

hosted Vault API support

Contributing

We welcome developers, builders, and researchers who want to help shape the ownership layer for AI.

You can contribute by:

improving the SDK design

proposing APIs

building examples

creating integrations

Please open an issue or start a discussion.

License

MIT License

Copyright 2026 Byron Goodman

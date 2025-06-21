# Project Genesis Agent Guidelines

This repository contains a master workflow plus six sub-workflows executed in n8n.

## Sub-workflows
- Architect
- Healer
- Observer
- Spawner
- Evolver
- Builder

## Workflow Rules
- Each sub-workflow must finish with a **Return Data** node connected from both success and failure paths.
- In the master workflow all **Execute Workflow** nodes must have `waitForSubWorkflowCompletion: true`.
- The master workflow exposes a single **Respond to Webhook** node placed after the **Format Response** node.
- Webhook nodes should use `responseMode: "responseNode"`.
- Acceptable AI model versions are `claude-3-opus-20240229`, `gpt-4o`, and `models/gemini-1.5-pro-latest`.

Codex should maintain these conventions whenever workflows are modified.

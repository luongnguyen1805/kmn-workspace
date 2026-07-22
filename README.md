# KMN Strategy

> **Knowledge. Memory. Navigation.**
>
> A lightweight methodology for organizing repository knowledge directly alongside the project.

## Overview

**KMN (Knowledge, Memory, Navigation)** is a repository-centric methodology for helping both humans and AI agents efficiently understand, navigate, and maintain projects.

Instead of relying on external knowledge bases, MCP servers, vector databases, or separate knowledge management applications, KMN stores project metadata inside the repository as structured, version-controlled Markdown.

The implementation of this methodology is called the **KMN-Layer**.

A KMN-Layer forms a lightweight **metadata layer** that exists alongside the primary project content while remaining completely independent from it.

The primary project remains the single source of truth.

# Motivation

Modern AI coding assistants can read source code extremely well, but they often spend significant effort rediscovering repository structure and repeatedly loading irrelevant files.

Projects frequently attempt to solve this with:

* large instruction prompts
* external documentation systems
* MCP servers
* vector databases
* separate knowledge management tools

These approaches can be effective, but they also introduce additional infrastructure, synchronization, indexing, and maintenance.

KMN takes a simpler approach:

> Keep repository knowledge inside the repository.

Repository knowledge evolves together with the project, can be reviewed like source code, and requires no external services.

# KMN Principles

## Knowledge

Describe how the project is designed.

Knowledge captures relatively stable information

Knowledge answers:

> **How does this work?**

## Memory

Preserve operational experience.

Memory records long-term lessons learned during development

Memory answers:

> **What have previous contributors learned?**

## Navigation

Enable progressive discovery.

Navigation provides a lightweight map of the repository, allowing agents to locate relevant information before opening implementation files.

Navigation answers:

> **Where should I look?**

# KMN-Layer

A **KMN-Layer** is the metadata layer implementing the KMN strategy.

Layer typically contains:

```text
.navigation/
    Index.md
    {name}.md

.knowledge/
    Index.md
    {topic}.md

.memory/
    Index.md
    {topic}.md
```

These folders contain metadata only.

They are not part of the primary project implementation.

# Metadata Layer

The KMN-Layer forms an independent metadata layer.

```
Repository

├── Primary Content
│   ├── Source Code
│   ├── Documentation
│   ├── Specifications
│   ├── Assets
│   └── ...
│
└── KMN-Layer
    ├── .navigation
    ├── .knowledge
    └── .memory
```

The metadata layer exists solely to assist discovery and understanding.

Primary project content should never depend upon the metadata layer.

Likewise, metadata should summarize and guide, never replace the primary content.

# Progressive Discovery

Rather than reading an entire repository, KMN encourages progressive discovery:

```text
Navigation
        ↓
Relevant Knowledge
        ↓
Relevant Memory
        ↓
Primary Content
```

Agents should expand exploration only when additional context is required.

This minimizes unnecessary repository exploration while improving task focus.

# Repository-Local

KMN intentionally keeps knowledge local.

Each metadata layer is responsible only for its own area of the repository.

Large repositories naturally become a hierarchy of small KMN-Layer rather than one centralized knowledge base.

This keeps metadata:

* modular
* maintainable
* discoverable
* scalable

# Benefits

* Repository-local
* Human-readable
* Version controlled
* No external infrastructure
* Minimal setup
* AI-friendly
* Works offline
* Independent of programming language
* Independent of AI model

# Relationship to External Knowledge Systems

KMN is not intended to replace MCP servers, vector search, or enterprise knowledge systems.

Instead, it provides a lightweight repository-native foundation.

Projects may later index a KMN-Layer using external retrieval systems if desired, while continuing to maintain repository knowledge as ordinary Markdown.

# Design Goals

The KMN strategy aims to:

* reduce unnecessary repository exploration
* improve AI-assisted development
* preserve long-term repository knowledge
* separate metadata from implementation
* encourage progressive discovery
* keep documentation easy to maintain

The guiding philosophy is simple:

> Keep project knowledge where the project lives.

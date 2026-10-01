# Jerome Pasquero

I am an AI and technology leader who still likes to build things.

My work has spanned machine learning, applied AI, product development, research, and engineering leadership. Outside of larger commercial projects, I regularly build systems to explore technologies, solve problems I actually have, and understand new tools from the inside.

Most of my substantial development repositories are private. Some contain commercial IP, some integrate with private infrastructure, and some are simply software I actively use rather than software I intend to distribute.

This page documents a selection of those projects, their architecture, and some of the engineering decisions behind them. I am happy to walk through the implementation and selected code where appropriate.

## Selected Projects

### AI Vibe

A platform for understanding how organizations use generative AI and identifying opportunities for practical AI adoption.

The system combines a structured database of more than 1,500 workplace tasks with semantic search, embeddings, generative models, organizational assessments, and an AI based interview system.

**My role:** Co founder and CTO

**Technologies:** Python, Cohere models and embeddings, Supabase, agent based workflows, semantic retrieval

**Source:** Private

### Synthetic Task Catalogs

A pipeline for generating large volumes of realistic workplace tasks and reducing them to a clean canonical catalog.

Tasks are generated from seeded domain packs using locally hosted open weight models, embedded, clustered by semantic similarity, normalized into consistent phrasing through verb mapping and removal of tool and context specific terms, then merged across clusters in embedding space. The output is a canonical task table, embeddings for each canonical task, and a mapping from every generated task back to the canonical form it belongs to.

The generation is the easy part. The interesting work is everything after it: deciding when two differently worded tasks are in fact the same task, and doing that consistently enough to build a catalog on. The pipeline pairs automated thresholds with an interactive review tool for keeping, renaming, splitting, or dropping clusters.

**Technologies:** Python, Ollama with open weight models, OpenAI embeddings, similarity based clustering, UMAP visualization, interactive review tooling

**Source:** Private

### Synthetic Banking Communication Data

A generator that produces synthetic small business banking relationships for churn prediction and customer relationship analysis.

Each generated customer has a loan, a risk profile, a communication persona, and a complete history: emails, chat messages, support tickets, call summaries, internal memos, underwriting notes, compliance notes, and the financial documents those messages refer to. Communication style follows from persona and context rather than being assigned at random, so informal personas produce short messages with typos and casual phrasing while formal ones stay polished, and a single customer is handled by several agents over time the way they would be inside a real institution.

Datasets like this are valuable precisely because the real equivalent cannot be shared. Current runs produce a thousand customers and tens of thousands of messages, with an optional local LLM pass that rephrases generated text to reduce the templated feel.

**Technologies:** Python, pandas, Ollama, persona driven generation, Markdown document synthesis

**Source:** Private

### LLM Based Contact Classification

A tool for scoring and classifying large contact lists against a defined commercial objective.

Scoring dimensions, rubrics, and additional classifications live in JSON profiles rather than in code, so the same pipeline can evaluate the same contacts against entirely different objectives: potential clients for one venture, data partners or strategic partners for another. Contacts are processed in batches, with caching, retries, and a shared client that puts locally hosted and hosted commercial models behind a single interface.

**Technologies:** Python, Ollama, OpenAI and Claude APIs, profile driven rubrics, batch processing

**Source:** Private

### Personal Finance Platform

A self hosted system for consolidating financial accounts, investments, holdings, fees, and historical performance across multiple financial institutions.

The project explores financial data ingestion, normalization, account reconciliation, investment analytics, and privacy conscious AI assisted development.

**Technologies:** TypeScript, Node.js, PostgreSQL, APIs, MCP, self hosted infrastructure

**Source:** Private

### Home Energy Platform

A system for collecting and analyzing energy usage across my home, including heating, cooling, electric loads, an EV, and environmental telemetry.

It combines data from multiple devices and APIs into a common historical dataset that can be used to understand consumption patterns and eventually optimize energy usage.

**Technologies:** Python, APIs, Docker, time series data, home automation, IoT

**Source:** Private

### Home Infrastructure

A small collection of Linux systems that run storage, media, backups, monitoring, networking, UPS management, and home automation services.

This has increasingly become a playground for experimenting with lightweight distributed infrastructure, remote administration, containers, observability, and resilient services.

**Technologies:** Debian, Docker, Tailscale, NUT, systemd, NAS storage, Linux networking

**Source:** Private

### Camera and Event Processing

A self hosted video pipeline integrating consumer cameras with local streaming and event processing infrastructure.

The project includes extracting video streams from devices not originally designed for this kind of integration, transcoding and stream management, and experimentation with motion triggered processing.

**Technologies:** Docker, go2rtc, FFmpeg, RTSP, HEVC, event driven processing

**Source:** Private

### Family Learning App

A small web application I built when my daughter started high school, to help her practice quiz questions for her studies. It covers multiple choice quizzes and French dictation exercises.

Quizzes are plain JSON files per subject, and the application tracks which questions each child has already been asked so a set can be worked through without repetition. The dictation module plays back pre generated audio for each sentence, then compares what was typed against the original using fuzzy and accent insensitive matching and highlights exactly where the two differ.

It is the smallest project listed here and the one that gets used the most.

**Technologies:** Python, Flask, SQLite, audio playback, text similarity matching

**Source:** Private

## About the Code

I keep most of my current development repositories private because they contain proprietary work, private infrastructure details, or projects that are not intended for public distribution.

I am happy to walk through the architecture, implementation decisions, and selected code where appropriate.

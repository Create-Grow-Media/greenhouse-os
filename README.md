# Greenhouse OS

A self-hosted operating system for a team of AI agents. It runs on your own
machine in Docker and you use it through one web interface on a desktop or a
phone.

> **Status: early prototype.** This repository holds no running code yet. It
> is the starting point for the platform described below.

## The goal

One self-contained program that runs a team of agents without depending on any
outside chat service to hold its state.

- **A workspace for each agent.** Every agent gets its own sandboxed space with
  only the tools its role needs, like an office with the right equipment in it.
- **One record of the work.** Tasks, decisions and the evidence behind them are
  kept in the platform's own store, with backups and recovery.
- **Connections in one place.** Each outside app shows its status (connected,
  expiring, broken or not connected). Secrets live in a vault, agents never see
  them directly, and each agent gets only the access its role allows. Every use
  is logged.
- **Approval before consequence.** Reads, drafts and status checks can run
  straight away. Sends, spending, live changes and deletions wait for a person
  to confirm them.
- **Voice as another way in.** Voice uses the same tasks, tools and permissions
  as the screen, not a separate, weaker assistant.
- **A widget library.** Agents show their work with approved interface
  components for projects, agents, deliverables and connections. They don't
  inject arbitrary code into the interface.

## How it will run

- **Docker Compose** brings up the services together: the database, the agent
  services, the connection service and the web interface.
- **Persistent data** lives in named volumes, with a documented backup and
  restore.
- **The web interface** can be added to a phone or desktop home screen like an
  app. A desktop wrapper may come later.
- The same services can move to another host without changing how they're used.

Docker packages the services. It doesn't reduce the memory or disk they need,
so check capacity before building images.

## What this repository will not contain

- credentials, tokens or connection settings;
- client names, client data or private history;
- configuration copied from any existing system.

Examples and demo data are fictional.

## Roadmap

1. Task, decision and evidence API, with sample data for the interface.
2. Docker Compose setup with persistent storage and backups.
3. Web interface: mission control, project canvas and connections.
4. Vault and credential broker with role-scoped access.
5. Agent workspaces and the approval service.
6. Voice.

## Licence

Not chosen yet. Until a licence is added, all rights are reserved.

# Database Repo Architecture

## Purpose

This document explains why the database has its own repo and how other repos should use it.

## First-Class Component Role

The database is a first-class platform component because it defines:

- durable data shape
- operational query surfaces
- migration risk
- cost characteristics
- blast radius across services and reports

That means database governance should not be scattered across application repos.

## What Lives Here

- approved model registry
- schema artifacts
- migration artifacts
- important query catalog
- cost and blast-radius analyses

## What Does Not Live Here

- service-specific DTOs
- UI-specific display models
- prompt templates
- business logic that belongs in Facts, Modeling, Narrative, or Orchestrator

## Cross-Repo Usage Rule

Other repos must reference this repo when they:

- propose schema changes
- create migrations
- add or change important queries
- propose indexes or retention changes
- assess blast radius for persistence changes

## Human Governance Rule

Database changes are not complete until:

- the approved model reference is cited
- affected queries are identified
- cost and blast-radius review is documented
- human DB approval is recorded

# Query Catalog Specification

## Purpose

This document defines the minimum structure for cataloging important queries.

## Required Fields Per Query

- query id
- owner
- consuming service
- business purpose
- expected frequency
- latency sensitivity
- cost sensitivity
- schema dependencies
- required indexes
- reasoning for current shape
- failure impact

## Review Rule

Material query changes must document:

- why the query changed
- expected cost impact
- affected schema assumptions
- blast radius if the query degrades or breaks

## Drift Control

Important query paths should not proliferate without ownership and documented purpose.

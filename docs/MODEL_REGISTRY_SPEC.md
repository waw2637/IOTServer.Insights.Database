# Model Registry Specification

## Purpose

This document defines the minimum structure for the approved DB model registry.

## Required Fields Per Model

- logical entity name
- physical table name
- owner
- purpose
- primary key
- major foreign keys
- important indexes
- retention expectations
- dependent services
- dependent reports or query families
- current approved version

## Review Rule

Any schema proposal must reference the current approved model entry it changes.

## AI Rule

AI must not propose a new model without first checking whether an approved model already exists for the same domain concern.

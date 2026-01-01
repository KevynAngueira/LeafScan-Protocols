# LeafScan Data Collection Plan

## Project Overview

This repository defines the standardized data collection protocols for the **LeafScan Defoliation Estimation System**, a set of tools, models, and workflows designed to quantify corn plant defoliation in a scalable, objective, and field-deployable manner.

The LeafScan system replaces subjective visual estimation with a repeatable, tool-assisted digitization workflow that enables both **in-field usability** and **post-hoc validation at scale**.

---

## Purpose of This Data Collection Plan

This plan defines:
- Required materials
- Step-by-step data collection procedures
- Validation and quality control checks
- Metadata requirements
- Failure modes and re-collection criteria

The goal is to ensure that all collected data is:
- **Usable** by downstream systems
- **Comparable** across collectors and locations
- **Auditable** for validation and review

---

## Data Collection Modes

This plan explicitly supports **two distinct modes of data collection**, each with different requirements and expectations.

### Mode A: **Operational (Intended) Use**

This mode represents normal field operation by trained adjusters.

Characteristics:
- Conducted in real-world field conditions
- Focused on post-defoliation measurement only
- Relies on validated workflows and trained users

Constraints:
- No access to pre-defoliation ground truth
- Limited time per plant
- Emphasis on repeatability and robustness

This mode prioritizes **scalability, usability, and consistency**.

---

### Mode B: **System Validation and Benchmarking**

This mode is used to evaluate and validate the performance of all LeafScan systems.

Characteristics:
- Conducted by a small group of senior data collectors
- Performed in controlled or semi-controlled environments
- Includes both healthy and defoliated plants

Additional requirements:
- Measurement of **true pre-defoliation leaf area**
- Measurement of **true post-defoliation leaf area**
- Capture of detailed locational metadata
- Data collector identification
- Intentional testing of edge cases and failure modes
- Redundant measurements where required

This mode prioritizes **ground truth accuracy and system evaluation** over speed.

---

## Audience

This data collection plan is intended for:
- Field adjusters
- Validation and benchmarking teams
- Researchers and engineers
- External reviewers and auditors

---

## Optional Reading: System Components

For researchers, engineers, or adjusters who wish to understand the **interconnected systems behind LeafScan**, a detailed description is available in [system_components.md](./protocols/09_system_components.md).

This section describes:
- LeafScan Digitization Pipeline
- LeafScan Defoliation Reconstruction Model
- LeafScan Physical Tool
- OpenMobile Application
- On-Device Validation Services
- Cloud Inference and Data Management Servers

> Note: Knowledge of these components is **not required** to operate LeafScan in the field.
> This material is provided to give context, deepen understanding, and foster engagement with the full system.

## Canonical Source and Artifacts

- The **Markdown files in `/protocol`** are the canonical source of truth
- PDFs and other exports in `/exports` are generated artifacts
- Checklists in `/checklists` are operational aids derived from the protocol

---

## Versioning and Change Control

All substantive changes to procedures, requirements, or interpretations must be:
1. Reflected in the relevant protocol file(s)
2. Recorded in `protocol/08_revision_history.md`
3. Committed with a clear, descriptive message

---

## Guiding Principles

- Procedures must be executable by a trained third party
- Ambiguity is treated as a defect
- If data cannot be validated, it must not be collected
- Physical constraints are preferred over algorithmic complexity





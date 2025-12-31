# LeafScan Data Collection Plan

## Project Overview

This repository defines the standardized data collection protocols for the **LeafScan Defoliation Estimation System**, a set of tools, models, and workflows designed to quantify corn plant defoliation in a scalable, objective, and field-deployable manner.

The LeafScan system replaces subjective visual estimation with a repeatable, tool-assisted digitization workflow that enables both **in-field usability** and **post-hoc validation at scale**.

---

## System Components

The LeafScan ecosystem consists of the following interdependent systems. Each system imposes specific constraints and requirements on data collection, which are explicitly addressed in this plan.

### 1. **LeafScan Digitization Pipeline**
*A leaf-agnostic, low-cost, and scalable digitization workflow*

LeafScan is a set of scripts and procedures that process short videos of a leaf being slid across a specialized tool. From these videos, the system reconstructs and measures the **post-defoliation leaf area** by aggregating unique leaf segments observed through a constrained viewing window.

Key properties:
- Leaf-agnostic (applicable to long-leaf crops)
- Low computational complexity
- Designed for field conditions
- Robust to partial defoliation and fragmentation

---

### 2. **LeafScan Defoliation Reconstruction Model**
*A lightweight regression model for pre-defoliation area estimation*

This model predicts the **original pre-defoliation leaf area** using post-defoliation measurements produced by the LeafScan pipeline. It enables estimation of defoliation percentage without requiring pre-damage imagery in operational settings.

Key properties:
- Parsimonious and interpretable
- Trained on physically meaningful measurements
- Designed to generalize across damage patterns

---

### 3. **LeafScan Physical Tool**
*A constrained capture environment for reliable digitization*

The LeafScan tool consists of:
- A **pink rectangular frontpiece** with a rectangular cut-out (the *view window*)
- A **blue rectangular backpiece**, offset to create a sliding channel

A leaf is manually slid across the tool, exposing successive leaf segments through the view window. The tool enforces:
- Fixed scale
- Controlled background
- Consistent orientation
- Simplified computer vision assumptions

This physical constraint is foundational to the performance of all downstream systems.

---

### 4. **OpenMobile Application**
*A mobile bridge between field collection and cloud inference*

OpenMobile is a mobile application that enables trained adjusters to:
- Capture standardized *LeafScan videos*
- Run **on-device validation** to determine video usability
- Upload validated data to cloud servers
- Retrieve inference results and finalized defoliation reports

The application is designed to function in **low-connectivity field environments**, deferring heavy computation until connectivity is available.

---

### 5. **On-Device Validation Services**
*Lightweight quality assurance for field-captured data*

Validation services run locally on mobile devices to determine whether a captured video is suitable for inference. These services are enabled by the constrained physical design of the LeafScan tool and include:

1. **Tool Presence Validation**
   - Detects the LeafScan tool using a PCA-based classifier (*eigen-tool detection*)

2. **Leaf Motion Validation**
   - Confirms that a leaf is actively sliding across the view window
   - Uses changes in contour area, perimeter, and compactness across key frames

These checks prevent unusable data from entering the cloud pipeline.

---

### 6. **Cloud Inference and Data Management Servers**
*A centralized source of truth*

Cloud servers:
- Receive validated videos from all adjusters
- Automatically schedule inference jobs
- Store raw data, metadata, and results
- Generate defoliation reports across plants, fields, and time

These servers function as the **authoritative database** for all operational and analytical outputs.

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

### Mode A: **System Validation and Benchmarking**

This mode is used to evaluate and validate the performance of all LeafScan systems.

Characteristics:
- Conducted by a small group of trusted, trained data collectors
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

### Mode B: **Operational (Intended) Use**

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

## Audience

This data collection plan is intended for:
- Field adjusters
- Validation and benchmarking teams
- Researchers and engineers
- External reviewers and auditors

---

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

# LeafScan-Protocols

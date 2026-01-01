# 00 – Scope and Objectives

**Audience:** Researchers, Field Adjusters, Project Managers, and Reviewers  
**Purpose:** Define the boundaries, goals, and expected outcomes of the LeafScan data collection project.

---

## 1. Project Scope

### Purpose
To clearly define what the LeafScan system is intended to measure, the constraints under which data is collected, and the expected uses of the resulting data.

### Description
LeafScan is designed to provide a **repeatable, objective, and scalable** method for estimating corn leaf defoliation. It encompasses:

1. **Physical tools** – specialized LeafScan device for standardized leaf capture.
2. **Data capture workflow** – videos of leaves slid across the tool.
3. **Mobile and cloud software** – OpenMobile for data entry, annotation, and cloud synchronization.
4. **Reconstruction models** – algorithms to estimate original leaf area and defoliation percentage.

Data collected will be used to:

- Quantify **post-defoliation leaf area**  
- Train and validate **pre-defoliation reconstruction models**  
- Benchmark system performance under varied environmental and leaf conditions  
- Provide operational guidance for insurance, research, or precision agriculture applications

---

### System Connection
Establishing scope ensures that all personnel, from field adjusters to data scientists, have a shared understanding of the system boundaries.  
This reduces inadvertent protocol violations and aligns expectations across teams.

---

## 2. Objectives

### Objective 1 – Operational Data Collection
**Purpose:** Enable adjusters to collect consistent, high-quality data under real-world field conditions.

**Approach:**

- Collect post-defoliation leaf videos using the LeafScan tool
- Record base widths and remaining leaf length
- Annotate field, plant, and leaf IDs in OpenMobile
- Ensure videos pass on-device validation before upload

**System Connection:**  
This objective ensures that operational users contribute data usable for routine inference while minimizing the risk of invalid captures.

---

### Objective 2 – Validation and Benchmarking
**Purpose:** Generate ground-truth datasets to assess LeafScan system accuracy and robustness.

**Approach:**

- Measure pre- and post-defoliation leaf area using calibrated leaf area meters
- Apply controlled simulated defoliation patterns
- Capture video and measurements for benchmarking edge cases
- Record detailed metadata for system evaluation (lighting, background, leaf type, damage patterns)

**System Connection:**  
Provides a high-fidelity reference to quantify model error and system reliability across real-world and extreme conditions.

---

### Objective 3 – Standardization and Auditing
**Purpose:** Ensure that all collected data is traceable, comparable, and auditable.

**Approach:**

- Use structured multilevel annotations: Field → Plant → Leaf → Measurements & Videos
- Record metadata for collector identity, tool version, and capture conditions
- Implement on-device and cloud-based validation checks
- Maintain revision-controlled protocols and checklists

**System Connection:**  
Enables reproducibility and external review while preserving dataset integrity for long-term research and operational use.

---

### Objective 4 – Scalability and Usability
**Purpose:** Collect large volumes of data efficiently without sacrificing quality.

**Approach:**

- Optimize workflow for field adjusters with minimal training
- Standardize tool design and video capture procedure
- Provide mobile app guidance and automated validation
- Prioritize low-complexity, repeatable tasks

**System Connection:**  
Supports deployment across multiple regions and users while keeping cognitive load low and minimizing operator-induced errors.

---

## 3. Key Deliverables

- **Operational Dataset:** Post-defoliation leaf measurements and videos, ready for model inference.
- **Validation Dataset:** Pre- and post-defoliation ground truth for benchmarking and model training.
- **Protocols and Checklists:** Formalized procedures for operational and validation data collection.
- **Training Materials:** Step-by-step guidance for field personnel, including video capture and app workflow.

---

## 4. Out of Scope

- Analysis beyond corn leaf defoliation (other crops are not supported)  
- Defining standard adjustment procedures (LeafScan **augments**, but does not replace, NCIS adjuster training and existing guidance)

---

## 5. Summary

This document establishes **the boundaries, goals, and expected outputs** of the LeafScan data collection system.  
It serves as a reference for all subsequent materials, ensuring clarity and consistency for both field and validation workflows.


# 01 – Materials and Preparation

This document defines **all preparation requirements** that must be satisfied *before* LeafScan data collection begins.

Preparation requirements are divided into:
- **Operational Protocols** – required for all field use  
- **Validation Protocols** – extensions applied only during system validation and benchmarking  

If any required preparation step is not met, **data collection must not proceed**.

---

## Part I – Operational Protocols  
*(Applies to all LeafScan data collection)*

---

### Section A – Operational Materials

#### Purpose  
To ensure all physical and digital tools required for LeafScan data collection are present and functional before entering the field.

#### Description  
LeafScan relies on a constrained physical capture environment and standardized measurements.  
Missing, substituted, or malfunctioning equipment can invalidate an entire collection session.

#### Protocol  

**Required Equipment**
- LeafScan physical tool  
- Mobile device with OpenMobile installed  
- Precision ruler (≥ 1/16 inch or 1 mm resolution)  
- Leaf-safe marking method (fine-tip marker or tape)

**Device Readiness**
1. Confirm mobile device battery ≥ 50%.  
2. Confirm sufficient local storage for video capture.  
3. Confirm camera lens is clean and unobstructed.

#### System Connection  
Equipment gaps introduce systematic bias by selectively dropping difficult or time-constrained samples.  
This check protects dataset completeness, repeatability, and downstream inference integrity.

---

### Section B – Operational Operator Training

#### Purpose  
To ensure data collectors can correctly execute LeafScan procedures and recognize unusable data *before* submission.

#### Description  
LeafScan assumes baseline competency prior to field deployment.  
This section confirms readiness rather than providing in-field instruction.

#### Protocol  
1. Confirm the operator has completed LeafScan tool training.  
2. Confirm the operator understands:
   - Proper LeafScan tool handling  
   - What constitutes a valid LeafScan video  
   - Common failure modes requiring re-capture  
3. Confirm completion of OpenMobile training.  
4. Confirm the operator can:
   - Create Plant and Leaf Annotations  
   - Assign Leaf ID, Plant ID, and Field ID  
   - Record leaf length and base widths  
   - Attach LeafScan videos to annotations  

#### System Connection  
Operator variability is the dominant source of field data failure.  
Ensuring minimum competency reduces invalid captures, prevents unnecessary cloud inference, and improves cross-adjuster consistency.

---

## Part II – Validation Protocols  
*(Extension of Operational Protocols)*

All operational preparation requirements apply unless explicitly extended below.

---

### Section C – Validation Materials

#### Purpose  
To ensure validation data includes accurate, repeatable ground-truth measurements and controlled defoliation capability.

#### Description  
Validation mode introduces additional measurement and manipulation steps that are not required during normal operation.

#### Protocol  

**Ground Truth Measurement**
- Commercial leaf area meter  
- Calibration reference (if applicable)

**Simulated Defoliation**
- Scissors  
- Standard hole punch (optional)

**Documentation and Handling**
- Notebook or CSV file for recording measurements  
- Cleaning materials for measurement equipment  

1. Verify calibration status of the leaf area meter.  
2. Confirm measurement device settings are known and reproducible.

#### System Connection  
Validation benchmarks are only as reliable as their reference measurements.  
Uncalibrated instruments or inconsistent settings invalidate error analysis and model evaluation.

---

### Section D – Validation Operator Training

#### Purpose  
To ensure validation personnel can reliably generate ground-truth data and controlled failure cases.

#### Description  
Validation data collection requires additional technical skill beyond operational use.  
Personnel must be capable of producing **repeatable measurements**, not just valid LeafScan captures.

#### Protocol  
1. Confirm certification for LeafScan validation protocol.  
2. Confirm training on:
   - Commercial leaf area meter operation  
   - Measurement repeatability and stability checks  
3. Confirm training on:
   - Controlled, intentional defoliation methods  
   - Avoiding accidental tearing or distortion  
4. Confirm understanding of:
   - Validation metadata requirements  
   - CSV or notebook recording standards  

#### System Connection  
Ground-truth error propagates directly into model evaluation metrics.  
Trained validation personnel ensure observed system error reflects algorithmic performance rather than human inconsistency.

---

### Section E – Task Assignments and Edge-Case Quotas  
*(Validation Mode Only)*

#### Purpose  
To ensure systematic coverage of edge cases, stress conditions, and known failure modes during validation.

#### Description  
Task assignments define **quotas**, not sequential steps.  
They are applied opportunistically during normal per-leaf processing and recorded for later analysis.

Detailed definitions, rationale, and expected outcomes for each task are documented in a **separate Task Assignment file**.

#### Protocol  
1. Review the task assignment sheet prior to entering the field.  
2. During leaf-level data collection:
   - Apply assigned transformations when appropriate  
   - Do not alter the core data collection sequence  
3. For each transformed leaf, record:
   - Leaf ID  
   - Transformation applied  
   - System outcome (pass / fail / ran)  
   - Adjuster assessment of acceptability  
4. Ensure all assigned quotas are met before concluding collection.

#### System Connection  
Edge cases rarely occur naturally and are underrepresented in field data.  
Explicit task assignments ensure validation datasets adequately probe system limits and failure boundaries.

---

### Section F – Pre-Field Readiness Confirmation

#### Purpose  
To provide a final go/no-go checkpoint before data collection begins.

#### Description  
This confirmation prevents partially prepared sessions from entering the dataset.

#### Protocol  
- [ ] Operational materials confirmed  
- [ ] Operational training confirmed  
- [ ] Validation materials confirmed (if applicable)  
- [ ] Validation training confirmed (if applicable)  
- [ ] Task assignments reviewed (if applicable)

#### System Connection  
Clear readiness gates improve auditability, reduce protocol drift, and protect downstream trust in collected data.


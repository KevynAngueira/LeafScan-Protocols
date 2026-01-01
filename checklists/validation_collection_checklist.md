# Validation Data Collection Checklist  
(LeafScan – System Validation and Benchmarking)

This checklist **extends the Operational Data Collection Checklist**.  
All operational requirements apply unless explicitly superseded.

This protocol follows the timeline:
**Pre-Defoliation Area → Simulated Defoliation → Post-Defoliation Area**

---

## A. Personnel Requirements (Additional)
- [ ] Data collector certified for LeafScan validation protocol
- [ ] Trained on commercial leaf area meter operation
- [ ] Trained on standardized simulated defoliation methods
- [ ] Understands edge and failure case testing

---

## B. Required Equipment (Additional)

### Ground Truth Measurement
- [ ] Commercial leaf area meter
- [ ] Calibration reference (if applicable)

### Simulated Defoliation
- [ ] Scissors
- [ ] Standard hole punch (optional)

---

## C. Task Assignment (Validation Quota)

- [ ] Adjuster assigned validation quota
- [ ] Validation trials applied **during normal data collection**
- [ ] Trials may be applied at any point, at adjuster discretion
- [ ] Each trial logged in CSV with:
  - [ ] Trial type
  - [ ] Field, Plant, and Leaf ID
  - [ ] System pass/fail
  - [ ] Whether data was processed or rejected

> Detailed trial definitions and failure criteria are documented separately.

---

## D. Pre-Defoliation Ground Truth Measurement

### Timing
- [ ] Completed **before any simulated defoliation**

### Identification
- [ ] Leaf ID assigned
- [ ] Plant ID recorded
- [ ] Field ID recorded

### Measurement
- [ ] Entire intact leaf measured
- [ ] Pre-defoliation area recorded
- [ ] Measurement device model logged
- [ ] Measurement repeated if unstable

---

## E. Simulated Defoliation Application

### Timing
- [ ] Applied **after pre-defoliation measurement**
- [ ] Applied **before LeafScan video capture**

### Defoliation Pattern
- [ ] Method selected and recorded:
  - [ ] Edge removal
  - [ ] Hole punching
  - [ ] Mid-leaf segment removal
  - [ ] Mixed pattern

### Constraints
- [ ] First X inches left undamaged  
      (unless explicitly testing base-width failure)

### Documentation
- [ ] Defoliation percentage estimated and recorded
- [ ] Estimation performed by different collector (if possible)
- [ ] Notes added for unusual patterns

---

## F. Post-Defoliation Ground Truth Measurement

### Timing
- [ ] Completed **after simulated defoliation**
- [ ] Completed **before LeafScan capture**

### Measurement
- [ ] Entire defoliated leaf measured
- [ ] Same meter used as pre-defoliation
- [ ] Device settings unchanged
- [ ] Measurement repeated if ambiguous

---

## G. LeafScan Video Capture & Validation
(All Operational checklist steps apply)

- [ ] Video captured **after simulated defoliation**
- [ ] System validation passed or failed
- [ ] Adjuster visual review completed
- [ ] Outcome logged for validation analysis

---

## H. Edge Case and Failure Testing (As Assigned)

### Capture Failures
- [ ] Partial scan
- [ ] Interrupted motion
- [ ] Folding or twisting
- [ ] Tool partially out of frame

### Environmental Stress
- [ ] Suboptimal lighting
- [ ] Background interference

### Structural Extremes
- [ ] Severe defoliation
- [ ] Damaged base widths
- [ ] Irregular or narrow leaves

---

## I. Post-Collection Review
- [ ] All metadata fields complete
- [ ] Ground truth measurements consistent
- [ ] Validation trials correctly logged
- [ ] Deviations from protocol documented


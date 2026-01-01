# Validation Data Collection Checklist  
(LeafScan – System Validation and Benchmarking)

This checklist **extends the Operational Data Collection Checklist**.
All operational requirements apply unless explicitly superseded below.

---

## A. Personnel Requirements (Additional)
- [ ] Data collector is certified for LeafScan validation protocol
- [ ] Data collector is trained in commercial leaf area meter operation
- [ ] Data collector is trained in standardized simulated defoliation methods
- [ ] Data collector understands required edge and failure case testing

---

## B. Required Equipment (In Addition to Operational Mode)

### Measurement and Ground Truth
- [ ] Commercial leaf area meter
- [ ] Leaf area meter calibration reference (if applicable)
- [ ] Precision ruler (minimum 1/16 inch or 1 mm resolution)
- [ ] Temporary leaf-safe marking method (fine-tip marker or tape)

### Simulated Defoliation
- [ ] Scissors
- [ ] Standard hole punch (optional)

### Documentation
- [ ] Camera or mobile device for still photos (may be same device)
- [ ] Cleaning materials for measurement equipment

---

## C. Leaf Selection (Pre-Defoliation)
- [ ] Leaf selected **before any defoliation is applied**
- [ ] Leaf is visually healthy and undamaged
- [ ] Leaf length sufficient to support segmented reconstruction analysis
- [ ] Leaf accessible for measuring, scanning, and applying defoliation  
      **without removal, tearing, or stretching**

---

## D. Pre-Defoliation Ground Truth Measurement

### Identification
- [ ] Leaf ID assigned prior to any measurement
- [ ] Plant ID and Field ID recorded

### Measurement
- [ ] Entire intact leaf measured using leaf area meter
- [ ] Pre-defoliation leaf area recorded
- [ ] Measurement device model recorded
- [ ] Measurement repeated if device reports error or instability

---

## E. Simulated Defoliation Application

### Timing
- [ ] Defoliation applied **only after** pre-defoliation measurements are complete

### Defoliation Pattern
- [ ] Defoliation method selected and recorded:
  - [ ] Edge removal
  - [ ] Hole punching
  - [ ] Mid-leaf segment removal
  - [ ] Mixed patterns
- [ ] Defoliation applied intentionally and deliberately
- [ ] No accidental tearing or crushing of leaf tissue

### Constraints
- [ ] First X inches remain **undamaged** unless explicitly testing failure cases

### Documentation
- [ ] **Explicit defoliation percentage estimated and recorded**
- [ ] Defoliation estimate performed by a **different data collector** than
      the one who applied the defoliation (preferred)
- [ ] Notes added for unusual or extreme patterns

---

## F. Post-Defoliation Ground Truth Measurement
- [ ] Entire defoliated leaf measured using the **same leaf area meter**
- [ ] Post-defoliation leaf area recorded
- [ ] Measurement device settings unchanged from pre-defoliation measurement
- [ ] Measurement repeated if segmentation is ambiguous

---

## G. LeafScan Video Capture
(All Operational Mode capture and validation steps apply)

- [ ] LeafScan video captured after simulated defoliation
- [ ] On-device validation passed
- [ ] Video accepted for upload

---

## H. Edge Case and Failure Mode Testing (As Assigned)

### Capture-Level Failures
- [ ] Partial scan (early termination)
- [ ] Non-continuous leaf motion
- [ ] Leaf folding or twisting
- [ ] Tool partially out of frame

### Environmental Stress
- [ ] Suboptimal lighting
- [ ] Background color interference

### Structural Extremes
- [ ] Severe defoliation
- [ ] **Damaged or irregular base widths**
- [ ] Narrow or irregular leaf shapes

---

## I. Post-Collection Review
- [ ] All required metadata fields populated
- [ ] Ground truth measurements internally consistent
- [ ] Notes added for anomalous samples
- [ ] Data flagged if deviations from protocol occurred


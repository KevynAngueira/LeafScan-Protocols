# OpenMobile Data Collection Workflow
(Operational and Validation Use)

---

## Purpose

This document defines the **canonical workflow** for using the OpenMobile application
to capture, validate, and submit LeafScan data.

Correct app usage ensures:
- Proper metadata association
- Traceability across field, plant, and leaf levels
- Reliable downstream inference and reporting

---

## Description

OpenMobile acts as the interface between field data collection and cloud-based
processing. It enforces structural constraints on data entry while enabling
on-device validation of captured media.

---

## Workflow Overview

The OpenMobile workflow follows a strict hierarchy:

1. Field
2. Plant
3. Leaf
4. Measurements and Media

This hierarchy must be respected to preserve data integrity.

---

## Operational Workflow

### 1. Field Initialization
- Create or select the correct Field
- Verify field identifier and location metadata

### 2. Plant Registration
- Create or select the correct Plant within the Field
- Verify plant identifier consistency

### 3. Leaf Registration
- Assign a unique Leaf ID
- Confirm leaf orientation and eligibility
- Leaf ID must be assigned **before** measurements or video capture

### 4. Base Width Entry
- Enter required base width measurements
- Verify units and measurement count
- Confirm values before proceeding

### 5. Video Capture
- Capture LeafScan video following the Video Capture Protocol
- Review playback immediately after capture

### 6. On-Device Validation
- Confirm tool presence validation passes
- Confirm leaf motion validation passes
- Videos failing validation must be recaptured

### 7. Submission
- Verify all required metadata fields are populated
- Submit data for upload when connectivity permits

---

## Common Errors

- Incorrect Leaf ID assignment
- Missing or incomplete base width measurements
- Submitting videos before validation passes
- Misassociation of leaf data to the wrong plant or field

---

## System Connection

OpenMobile enforces structural assumptions required by:
- Cloud inference scheduling
- Dataset consistency across collectors
- Auditability and post-hoc validation

Incorrect app usage can result in irrecoverable data loss or invalid inference results.


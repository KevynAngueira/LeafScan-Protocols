# LeafScan Video Capture Protocol
(Operational and Validation Use)

---

## Purpose

This document defines the **authoritative procedure** for capturing a valid LeafScan video.
A LeafScan video is the primary input to the digitization pipeline and must meet strict
physical and visual constraints to ensure reliable downstream processing.

This protocol defines **what constitutes a valid capture**. Companion training videos
illustrate correct and incorrect execution but do not supersede this document.

---

## Description

A LeafScan video records a leaf sliding continuously through the LeafScan tool’s
constrained view window. Each frame represents a fixed-scale cross-section of the leaf,
allowing the system to reconstruct post-defoliation leaf area from unique observed
segments.

LeafScan is designed to be run **non-destructively**. The leaf must remain attached
to the plant during capture and sufficiently intact to allow a continuous scan.

---

## Preconditions

- LeafScan tool is available and clean
- Mobile device has sufficient battery and storage
- Leaf meets eligibility requirements:
  - Accessible without damaging the plant
  - Fits fully within the tool channel
  - Can be held taut and flat
  - Sufficiently intact to allow continuous motion

---

## Capture Protocol

### 1. Tool and Camera Setup
- Entire LeafScan tool **must be visible** in the camera frame
- View window must be fully unobstructed
- Camera must remain stationary during capture
- Lighting must be sufficient to clearly distinguish leaf tissue

### 2. Leaf Positioning
- Leaf is inserted into the tool channel correctly
- Leaf is held taut and flat
- No twisting, folding, or bending is permitted

### 3. Leaf Motion
- Leaf must slide **continuously** through the view window
- Motion must be:
  - Single-directional
  - Smooth and uninterrupted
- No pauses, reversals, or backtracking
- Entire remaining leaf length must be scanned in one pass

### 4. Recording Constraints
- Recording starts before leaf enters the view window
- Recording ends only after leaf fully exits the view window
- No mid-scan stopping or restarting

---

## On-Device Validation

Captured videos are automatically evaluated by on-device validation services:

- Tool presence validation
- Leaf motion validation

Videos that fail validation **must not** be uploaded.

---

## Failure Modes (Non-Exhaustive)

- Tool partially out of frame
- Leaf motion stops or reverses
- Leaf folds or twists during scan
- View window obstructed
- Background color interference
- Insufficient lighting

---

## System Connection

This protocol enforces assumptions required by:
- Leaf segment uniqueness detection
- Fixed-scale area reconstruction
- Robust post-defoliation area estimation

Violations of this protocol directly degrade reconstruction accuracy and invalidate
defoliation estimates.


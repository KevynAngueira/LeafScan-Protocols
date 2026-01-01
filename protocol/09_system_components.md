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


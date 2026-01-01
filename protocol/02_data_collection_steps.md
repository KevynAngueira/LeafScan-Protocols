# 03 – Data Collection Steps

This document defines the **in-field execution steps** for LeafScan data collection.
It is designed to remove ambiguity during field work while also serving as a formal, auditable protocol for system validation, benchmarking, and external review.
All preparation steps are assumed complete per **01 – Materials and Preparation**.

Two data collection modes are defined:

- **Operational Mode** – standard field use by trained adjusters  
- **Validation Mode** – extended protocol for system testing and benchmarking  

> **Note on Audience**  
> This document is written primarily for adjusters performing data collection.  
> Sections labeled **System Connection** provide additional technical context for researchers, engineers, and reviewers.  
> These sections may be skipped during routine data collection without affecting protocol compliance.

---

# Part I – Operational Data Collection Protocol  
*(LeafScan – Intended Use)*

LeafScan is designed to **augment existing adjusting procedures**, not replace them.  
All plant and field selection decisions should follow standard adjusting guidance unless explicitly stated otherwise.

---

## Step 1: Select a Representative Plant

**Purpose**  
To select a plant that accurately reflects field-level defoliation and is suitable for LeafScan measurement.

**Description**  
The adjuster selects a representative corn plant following standard adjusting procedures.  
During selection, the adjuster verifies that the plant contains leaves suitable for LeafScan data collection.  

If no representative plants meet minimum requirements, the field is flagged and standard visual estimation procedures are used.

**Procedure**  
1. Select a corn plant representative of surrounding field conditions, following standard adjusting guidance.  
2. Inspect leaves on the plant **without removing them**.  
3. Confirm the plant contains leaves that:  
   - Fit within the LeafScan tool channel  
   - Can be held taut without tearing  
   - Do not show extensive damage across the first **X inches** from the leaf collar  
4. If determining growth stage requires plant removal:  
   - Select a nearby equivalent plant  
   - Determine growth stage following standard adjusting guidance  
5. If the plant does not meet LeafScan requirements:  
   - Select a different representative plant  
6. If no suitable representative plants are available:  
   - Flag the field for extensive damage in the app  
   - Defer to standard visual estimation procedures

**System Connection**  
Representative plant selection underpins all scaling from leaf-level measurements to plant- and field-level estimates.  
Allowing a formal fallback to visual estimation prevents biased datasets caused by forcing LeafScan on unsuitable material.

---

## Step 2: Per-Leaf Processing

The following steps are performed for each leaf on the selected plant.  
LeafScan is designed to operate **non-destructively**, with leaves remaining intact and attached to the plant during video capture.

---

### Step 2.1: Environment Check (Immediately Before Capture)

**Purpose**  
To ensure environmental conditions will not interfere with LeafScan video quality.

**Description**  
Environmental checks are performed immediately before each video capture.  
Lighting, background color, and glare directly affect tool detection.

**Procedure**  
1. Confirm lighting is even and sufficient.  
2. Ensure no strong glare appears on the LeafScan tool.  
3. Confirm background elements contain **no pink, red, or similar colors**.

**System Connection**  
Environmental variability directly impacts contour detection and tool localization.  
Performing this check immediately before capture reduces silent failures caused by changing conditions.

---

### Step 2.2: LeafScan Video Capture

**Purpose**  
To digitally capture the defoliated leaf in a controlled and repeatable manner while the leaf remains intact and attached to the plant.

**Description**  
The leaf is slid through the LeafScan tool while a video is recorded.  
Capture is performed with the **frontside of the leaf facing forward**.

**Procedure**  
1. Position the LeafScan tool around the leaf while it remains attached to the plant.  
2. Ensure the **entire tool** is visible in the frame.  
3. Start recording in OpenMobile.  
4. Slide the leaf smoothly through the tool:  
   - No pauses  
   - No reversals  
   - No folding  
5. Continue until the entire leaf length is scanned.  
6. Stop recording.

**System Connection**  
LeafScan processes video as a sequence of fixed-height segments.  
Capturing the leaf while attached preserves natural tension and alignment, reducing deformation-related errors.

---

### Step 2.3: Video Validation (Required Before Measurement)

**Purpose**  
To ensure the captured video is acceptable before any further handling of the leaf.

**Description**  
Validation occurs immediately after capture and consists of **two independent checks**: automated system validation and adjuster visual review.  
Both must pass for the video to be accepted.

**Procedure**  
1. Allow on-device validation to complete.  
2. Confirm automated checks pass:  
   - Tool presence validation  
   - Leaf motion validation  
3. Visually review the video to confirm:  
   - Entire tool remains in frame  
   - Leaf motion is continuous  
   - No folding, reversal, or obstruction occurs  
4. If **either** the system or the adjuster rejects the video:  
   - Discard the capture  
   - Re-capture the video before proceeding  
5. Only proceed once the video is accepted by **both** checks.

**System Connection**  
This two-factor validation prevents false positives where automated checks pass but subtle issues remain.  
Early rejection protects downstream inference and dataset integrity.

---

### Step 2.4: Leaf Identification and Physical Measurements

**Purpose**  
To record the physical measurements required to interpret the LeafScan video and estimate the leaf’s original area.

**Description**  
For each leaf, the adjuster records:  
- **Leaf number**  
- **Post-defoliation leaf length**  
- **Base width measurements** across the first X inches  

Measurements may be performed with the leaf still attached or removed for convenience.  
Leaf removal is optional and does not affect LeafScan operation.

**Procedure**  
1. Identify and record the **leaf number**.  
2. Measure and record the **remaining leaf length** from collar to tip.  
3. Identify the **leaf collar**, where the blade meets the plant.  
4. Hold the leaf taut with the **backside facing upward**.  
5. Measure and record the width at the collar.  
6. Mark a line **1 inch above the previous measurement**, perpendicular to the leaf.  
7. Measure and record the width at each marked interval.  
8. Flag any base width that is damaged or unmeasurable.  
9. Repeat until all **X base widths** are attempted.

**Notes on Damaged Base Widths**  
- Damaged base widths may be extrapolated from remaining measurements.  
- If too many base widths are missing or damaged, the system will prevent completion of the leaf record.  
- In this case, the adjuster must select a different representative plant.

**System Connection**  
Leaf length calibrates the number of segments extracted from the video.  
Leaf number and base widths anchor reconstruction models used to predict original leaf area.  
Explicit damage flags allow the system to distinguish missing data from true geometry.

---

## Step 5: Repeat Across Leaves and Plants

**Purpose**  
To collect sufficient data for reliable field-level estimates.

**Description**  
The adjuster repeats per-leaf processing for each leaf on the selected plant, then repeats plant selection across **X representative plants** in key field locations.

**Procedure**  
1. Repeat Step 4 for each leaf on the plant.  
2. Select the next representative plant.  
3. Repeat Steps 3–4 until the required number of plants is reached.

---

## Step 6: Data Synchronization and Results Retrieval

**Purpose**  
To securely upload collected data, complete inference, and retrieve results.

**Description**  
After field collection, the adjuster must reach a location with reliable internet to synchronize all data with the cloud system.

**Procedure**  
1. Navigate to a location with reliable internet access.  
2. Open OpenMobile and initiate data synchronization.  
3. Confirm all:  
   - Leaf annotations  
   - Measurements  
   - LeafScan videos  
   have uploaded successfully.  
4. Wait for cloud inference to complete.  
5. Download and review results as required.

**System Connection**  
Explicit synchronization ensures data integrity, traceability, and consistent linkage between field data and inference results.

---

# Part II – Validation Data Collection Protocol  
*(System Validation and Benchmarking)*

> **Note:**  
> This protocol is an extension of the **Operational Mode**. All operational steps apply unless explicitly modified below.  
> Validation steps are interleaved **within Step 4: Per-Leaf Processing** of the operational protocol.  
> Timing for each validation substep is explicitly noted.

---

## Task Assignment / Edge Case Quotas

**Purpose**  
Ensure systematic coverage of edge and failure cases for benchmarking.

**Description**  
Before fieldwork, each adjuster receives a **task assignment sheet**:  
- Specifies quotas for extreme or unusual scenarios (e.g., severe defoliation, damaged base widths, partial scans, suboptimal lighting)  
- Adjusters may apply these transformations **at any point** during Step 4 per-leaf processing  
- Transformations are recorded in the CSV along with system pass/fail status

**Protocol**  
- Review task sheet before starting leaf collection.  
- During data capture, mark any leaves where a transformation was applied:  
  - Leaf ID  
  - Transformation type  
  - Observed system behavior (pass/fail)  
- Ensure all quotas are met before concluding fieldwork.

**System Connection**  
This ensures validation datasets adequately stress-test the system across predefined extreme conditions.  
A separate file will describe the purpose and expected outcome for each transformation.

---

## Step 2: Per-Leaf Processing

The following steps are are interleaved extensions to the **Per-Leaf Processing Operational Protocols**.  
All 3 steps must be completed before proceding to **Step 2.1 (Environment Check)**

---

## Step 2.a: Pre-Defoliation Leaf Area Measurement

**Purpose**  
Record baseline leaf area to quantify LeafScan prediction error.

**Description**  
Use a commercial leaf area meter to measure the intact leaf before any simulated or natural defoliation.

**Timing**  
**Before Step 2.1 (Environment Check)**

**Protocol**  
1. Assign Leaf ID, Plant ID, and Field ID (record in CSV or notebook).  
2. Measure full leaf area with the leaf area meter.  
3. Record pre-defoliation area.  
4. Repeat measurement if device reports instability.

**System Connection**  
Provides ground-truth reference for evaluating LeafScan’s post-defoliation predictions.

---

### Step 2.b: Simulated Defoliation

**Purpose**  
Create controlled, repeatable leaf damage for benchmarking reconstruction under varied conditions.

**Description**  
Defoliation is applied intentionally, following patterns from the task assignment sheet.

**Timing**  
Immediately **after Step 2.a (Pre-defoliation area)** and **before Step 2.1 (Environment Check)**.

**Protocol**  
1. Select defoliation pattern according to the assignment sheet.  
2. Apply defoliation carefully to avoid accidental tearing or crushing.  
3. Record defoliation details and approximate severity in CSV.

**System Connection**  
Controlled defoliation allows systematic evaluation of LeafScan accuracy across different severities and leaf types.

---

### Step 2.c: Post-Defoliation Leaf Area Measurement

**Purpose**  
Record remaining leaf area after defoliation to enable accurate defoliation benchmarking.

**Description**  
Use the same leaf area meter as pre-defoliation measurement.

**Timing**  
Immediately **after Step 2.b (Simulated Defoliation)** and **before Step 2.1 (Environment Check)**.

**Protocol**  
1. Measure leaf area with the meter.  
2. Record post-defoliation area in CSV.  
3. Ensure measurement settings match pre-defoliation measurement.  
4. Repeat if device instability occurs.

**System Connection**  
Together with pre-defoliation area, establishes true defoliation percentage for benchmarking.

---

## Step 3: Post-Collection Review

- Verify all validation data (pre/post area, defoliation, base widths, leaf number, leaf length, task assignments) are complete.  
- Flag anomalies.

---

### Step 4: Data Synchronization

- Upload all videos, annotations, and CSV records to cloud.  
- Wait for inference to finish.  
- Download and review results.


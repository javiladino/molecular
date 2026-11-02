---
# EXPERIMENT METADATA (eLabFTW Header)
title: "EXP-BM-2026-088: RNA Isolation and cDNA Synthesis"
category: "Molecular Biology"
tags: [rna-seq, rt-pcr, rna-extraction, cdna]
status: "In Progress"
privacy: "Restricted (Research Group Only)"
---

## 1. General Information and Change Control

| Parameter | Detail |
| :--- | :--- |
| **Principal Investigator** | Dr. Clara Morales |
| **Executed by** | MSc. Carlos Mendoza |
| **Linked Project** | PRJ-2026-BREAST-CANCER (`#PRJ-004`) |
| **Start Date** | 2026-10-26 |
| **Execution Location** | Laminar Flow Cabinet II B (Lab 302) |

---

## 2. Reagents, Equipment, and Inventory (eLabFTW Traceability)

> 💡 *Use internal eLabFTW item links to reference exact lot numbers and locations.*

### Reagents and Supplies
- [x] **Extraction Kit:** RNeasy Mini Kit (Qiagen) | **Lot:** `#QG-984211` | **Expiration:** 2027-04
- [x] **Reverse Transcriptase Enzyme:** SuperScript IV | **Lot:** `#INV-8820` | **Storage:** -20°C Freezer (Box A-4)
- [x] **RNase/DNase Control:** Nuclease-Free Water (Ambion) | **Lot:** `#AM-0012`

### Calibrated Equipment
- **Refrigerated Centrifuge:** Eppendorf 5424 R (ID: `EQ-CENT-02`)
- **Spectrophotometer:** NanoDrop One (ID: `EQ-ND-01`)
- **Thermal Cycler:** Bio-Rad T100 (ID: `EQ-TC-03`)

---

## 3. Step-by-Step Protocol (SOP-BM-012 v2)

### Phase A: Sample Lysis and RNA Extraction
1. Resuspend the cell tissue sample in **600 µL of Buffer RLT** supplemented with 10 µL/mL of $\beta$-mercaptoethanol.
2. Homogenize by vortexing at maximum speed for **30 seconds**.
3. Add 1 volume of 70% ethanol and centrifuge in an RNeasy spin column at **8,000 x g** for **15 seconds**.
4. Perform sequential washes with RW1 buffer (350 µL) and RPE buffer (500 µL).
5. Elute the purified RNA in **30 µL of nuclease-free water**.

### Phase B: cDNA Synthesis (Reverse Transcription)
Mix the following components in sterile 0.2 mL PCR microcentrifuge tubes:

| Component | Initial Concentration | Volume per Reaction (µL) |
| :--- | :--- | :--- |
| Template RNA | ~500 ng/µL | 2.0 |
| Oligo(dT)18 primer | 50 µM | 1.0 |
| dNTP Mix | 10 mM each | 1.0 |
| Nuclease-Free Water | — | 9.0 |
| **Subtotal** | | **13.0** |

*Incubate at 65°C for 5 minutes and immediately chill on ice for at least 1 minute.*

Add the final enzyme mixture:
- 5X SSIV Buffer: **4.0 µL**
- DTT (100 mM): **1.0 µL**
- RNaseOUT Inhibitor: **1.0 µL**
- SuperScript IV RT (200 U/µL): **1.0 µL**

**Thermal Cycler Program:**
- 23°C for 10 min (Annealing)
- 50°C for 10 min (Extension/Synthesis)
- 80°C for 10 min (Enzyme Inactivation)

---

## 4. Quality Control and Raw Results

### Purity and Concentration (NanoDrop)

| Sample ID | Conc. (ng/µL) | $A_{260/280}$ Ratio | $A_{260/230}$ Ratio | QC Status |
| :--- | :--- | :--- | :--- | :--- |
| M-2026-001 | 485.2 | 2.05 | 2.12 | Passed |
| M-2026-002 | 512.0 | 2.02 | 1.98 | Passed |
| Control (-) | 1.2 | 1.15 | 0.42 | N/A (Negative) |

### Attached Data Files

- 📁 [20261026_nanodrop_raw_export.csv](/data/20261026/20261026_nanodrop_raw_export.csv) *(Direct equipment export)*
- 🖼️ [20261026_bioanalyzer_RNA_integrity.png](/assets/20261026/20261026_bioanalyzer_RNA_integrity.png) *(RIN Verification = 9.2)*

---

## 5. Signatures and Audit Closure

> 🔒 **eLabFTW Digital Signature:**
>
> - **Status:** Signed and Locked against modifications.
> - **Signed by:** MS. Timna Bergmann
> - **SHA-256 Hash:** `9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08`
> - **Timestamp:** 2026-10-26 T 17:42:01 CEST
# TEPMT Standard  
**Translate – Edit – Proof for Machine Translation**

---

## 🔁 Overview

**TEPMT** defines a modular, AI-native workflow for high-quality, auditable translation pipelines.  
Each step is discrete, traceable, and automatable — enabling translators and systems to collaborate efficiently.

---

## 📚 Workflow Stages

### 1. Translate
**Input:** Source content  
**Output:** First-pass translation (by MT or AI model)

- May be raw MT or fine-tuned model output
- Must include language variant and domain tags
- Stored with origin metadata (e.g. model version, timestamp)

---

### 2. Edit
**Input:** Translated segment  
**Output:** Terminology- and tone-aligned segment

- Terminology harmonized (using glossary or Align step)
- Tone normalized per client preference (formal, neutral, etc.)
- Rewrite logged if auto-applied

---

### 3. Proof
**Input:** Edited segment  
**Output:** Verified, delivery-ready segment

- Target re-read for fluency, clarity, and factual match
- Errors flagged (automatically or by human reviewer)
- Final quality score assigned

---

## 🧾 Metadata Schema (used in TMX 2.0 or JSONL)

Each segment may include:

| Field | Description |
|-------|-------------|
| `tep_stage` | One of: `translate`, `edit`, `proof` |
| `score`     | Confidence/quality score (0.0–1.0) |
| `tone`      | e.g. `neutral`, `formal`, `friendly` |
| `editor`    | `ai`, `human`, or tool name |
| `timestamp` | ISO 8601 |
| `variant`   | e.g. `en-GB`, `sv-SE` |

---

## 🧩 Compatibility

TEPMT can be implemented via:

- Pauhu Clean / Align / Model / Trace
- External CAT tools or TM engines
- Custom in-house LLM workflows

All output can be stored in **TMX 2.0 with segment metadata** or in JSONL for retraining.

---

## 🔓 License

This standard is open and may be reused under [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/).


# Change Log
- Added `evidence_mode` flag with "strict" behaviour.
- Added standardized warning messages for missing and very short sections.

---

## Module 5: Guardrails
- **Inputs:** Draft summaries.  
- **Process:** Validate against boundaries:  
  - No hallucinations.  
  - No invented citations.  
  - Word limits enforced.  
  - All main sections included.  
- **Outputs:** Clean, validated summaries.

## Strict Evidence Mode

- The module supports an `evidence_mode` variable. Valid values include:
  - `evidence_mode = "strict"` (recommended default for research summarization)

- When `evidence_mode = "strict"`:
  - The summarizer must **only** include:
    - Claims
    - Equations
    - Results
    - Definitions
    that explicitly appear in the provided source text.
  - The summarizer must **not**:
    - Infer new results
    - Invent equations
    - Add citations or references not included in the paper
  - If the source text does not provide enough detail to summarize a section under strict mode, output:
    - `"The source text does not provide enough detail to summarize this section in strict evidence mode."`


## Section Warning Messages

- For each section, the guardrails must check:
  - Whether the section is **missing or empty**
  - Whether the section is **very short** (< 50 words)

- If a section is **missing or empty**:
  - Output:
    - `"Section skipped: no usable text was provided for this section."`

- If a section is **very short**:
  - Output:
    - `"Section very short: summary may be incomplete due to limited source text."`

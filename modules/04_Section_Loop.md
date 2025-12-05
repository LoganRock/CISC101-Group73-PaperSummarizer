# Change Log
- Added `summary_level` variable for controlling section summary length.
- Added conditional behaviour for "short" vs "detailed" summaries for each section.

---

## Module 4: Section Loop
- **Inputs:** Individual sections, figures, tables, equations.
- **Process:** Summarize each section, enforce constraints, attach visuals.
- **Outputs:** Section summaries with integrated figures/tables/equations.

## Summary Level Behaviour

- The module must respect a `summary_level` variable for each run. Valid values:
  - `summary_level = "short"`
  - `summary_level = "detailed"`

- For each section in the loop:

  - If `summary_level = "short"`:
    - Generate a compact summary of **1–2 sentences** for that section.
    - Do **not** generate bullet points.

  - If `summary_level = "detailed"`:
    - Generate:
      - A **short paragraph** summarizing the section.
      - **Plus** a bullet list of **3–5 key points** highlighting:
        - Main claims or findings  
        - Important methods, experiments, or datasets  
        - Critical results or conclusions  

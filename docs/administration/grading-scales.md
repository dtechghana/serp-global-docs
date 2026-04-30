# Grading Scales

Grading scales define how a numerical score maps to a grade label and remark. Each class is assigned one grading scale.

---

## Built-in Scales

sERP ships with the following built-in scales:

| Scale name | Description |
|------------|-------------|
| `primary` | Generic primary school scale (A–F) |
| `gh_bece` | WAEC BECE scale for Ghana (A1–F9) |
| `gh_wassce` | WAEC WASSCE scale for Ghana (A1–F9) |

These cannot be edited or deleted. If your country uses a different set of boundaries for the same grade labels, create a custom scale.

---

## Assigning a Scale to a Class

1. Go to **Academic → Classes**
2. Edit the class
3. Set the **Grading Scale** field
4. Click **Save**

All scores computed for students in that class will use the assigned scale from the next score entry onwards. Previously saved scores are not retroactively re-graded.

---

## Creating a Custom Scale

1. Go to **Settings → Academic Settings → Custom Grading Scales**
2. Click **Add New Scale**
3. Enter a **Scale Name** — use a short identifier with no spaces (e.g. `ng_waec`, `ci_bepc`)
4. Add each grade row:
    - **Grade label** (e.g. `A1`, `B2`, `Pass`)
    - **Minimum score** (inclusive lower bound)
    - **Maximum score** (inclusive upper bound)
    - **Remark** (e.g. `Excellent`, `Credit`)
5. Ensure all grade rows together cover 0–100 without gaps or overlaps
6. Click **Save Scale**

!!! warning "No gaps or overlaps"
    If the grade boundaries don't cover the full 0–100 range, scores falling in the uncovered range will return a blank grade. sERP does not validate for gaps — double-check your ranges.

---

## Editing a Custom Scale

1. Go to **Settings → Academic Settings → Custom Grading Scales**
2. Click **Edit** next to the scale
3. Modify grade boundaries or remarks
4. Click **Save**

!!! note
    Editing a scale affects all future grade calculations for classes using it. Scores already saved in the database are stored as raw numbers — the grade and remark are computed on display, so an edit takes effect immediately everywhere.

---

## Default Scale per Deployment

The active country's [academic framework](../deployment/country-profiles.md#academic-frameworks) specifies which scale name is used as the default for new classes. This default can always be overridden per class.

For Nigeria (`ng_basic`), the default is `primary`. For JSS and SSS classes, you should assign a `ng_waec`-style custom scale that uses the A1–F9 boundaries.

---

## Scale Name Reference

The scale name is the string stored in the class record and used by `GradingScales::fetchAll()` and `calculateGrade()`. When creating custom scales, choose names that:

- Are lowercase
- Use underscores (no spaces or special characters)
- Include the country prefix for country-specific scales (e.g. `ng_`, `ci_`)
- Are descriptive enough to distinguish at a glance in a dropdown (e.g. `ng_waec` not just `waec`)

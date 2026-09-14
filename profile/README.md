# profile/ — customer-specific constraints (reserved)

This folder is empty in the public release. When an idea workspace is prepared for one customer, it holds that customer's constraints, and the Director reads it at every start (RULES §8).

A profile may **restrict, never loosen**: write rules, git behaviour and "nothing outside the workspace" stay as defined in `RULES.md`. The profile shapes content and frame.

Planned files (the format is fixed with the first real profile):

| File | Read by | Purpose |
| --- | --- | --- |
| `profile.md` | Director | customer, department codes, default language, session budgets, contact person |
| `context.md` | collect | company goals and AI/data strategy (prefills the strategy-link field), department list for the interface round |
| `evaluation.md` | evaluate | effort-class thresholds for V6, applicable norms and certifications with contact persons for V8, house-specific anchors if any |
| `scope.md` | both | allowed topic areas and exclusions |

Until a profile exists, this README is the only file here and means "core defaults".

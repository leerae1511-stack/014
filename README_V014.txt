# Tool Pocket Generator V014

## Release status
User-validation build. Built directly from `Tool_Pocket_Generator_V012_FINAL.zip`.

## Source / provenance
- Starting source: `Tool_Pocket_Generator_V012_FINAL.zip`.
- V012 was unpacked and used as the sole working source for V014.
- V013 was NOT used as the source.

## Requested scope
One functional change only: **clearance processing and STL export**.

## V014 change
The clearance/STL path was rebuilt so that a valid closed sampled tool profile is first converted to one outward-cleared profile.

- Convex corners use sampled outward joins.
- Concave corners use offset-line intersections.
- Duplicate/degenerate offset points are removed.
- Offset loops/self-crossing loops are detected and resolved by retaining the outer resulting closed loop.
- Geometry Check validates the cleared profile, including self-intersection and triangulation.
- STL export uses the validated cleared profile, not the uncleared tool profile.
- STL export is blocked unless the cleared profile is valid and triangulates successfully.

## Explicitly not changed
- Detect Exact Tool Outline.
- New Tool / Import JSON workflows.
- Physical-grid confirmation and scaling.
- Workspace rectangle behaviour.
- Point editing and numbering.
- Straight / Curve editing behaviour.
- JSON save/import/export workflow.
- Existing profile close/dimension workflow.
- Tray/depth controls other than their existing use during STL export.

## Testing performed
- V012 source unpacked successfully.
- HTML JavaScript syntax check: PASS.
- Clearance algorithm tests: PASS on convex, concave and narrow-feature test profiles at multiple clearance values.
- Resulting cleared profiles were checked for self-intersection and ear-clipping triangulation.
- Brush V013 completed-profile data was used as a regression geometry source; its stored profile is closed and dimensioned from the physical grid.
- No claim is made that this replaces the user's iPad/Safari validation.

## User validation targets
- Brush: STL export must remain successful with clearance applied.
- Wrench: STL export must become successful with the same general clearance algorithm.
- Additional tool profiles should receive the same generic treatment; no tool-specific rules are used.

## Version alignment
All generator-visible V014 labels were updated in HTML, manifest, saved-tool storage key, STL solid name and exported STL filename.

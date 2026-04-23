# Hebrew App - Next Module Infrastructure Plan

## Goal
Finish all non-visual work for the Hebrew app and prepare a stable base for the next major module pass after Archetypes.

## Current Status
- Archetypes module is functionally complete (excluding visual front cards).
- Hebrew shell exists and supports embedded module routing.
- PWA baseline is active (manifest + service worker + manual update flow).

## Next Module Priority
1. **Kinky Scene Planner (Hebrew integration hardening)**
2. **Hypno Language Cards (Hebrew integration hardening)**

The planner is first because it has the highest behavior complexity and export/share flows.

## Planned Work Packages

### Package A - Planner Infrastructure Alignment
- Verify Hebrew planner embed UX parity with current English flow.
- Remove old/unused shell controls (share-link leftovers, sticky header assumptions).
- Add parent-shell fallback behavior for embed failures.
- Add planner-specific local data reset option in Hebrew shell.

### Package B - Planner Reliability Pass
- Validate save/load session loops from Hebrew shell entry points.
- Validate summary-open flow from saved sessions.
- Validate PDF/share trigger path from embedded context.
- Add explicit user-visible status when embed is loading or unavailable.

### Package C - Hypno Infrastructure Alignment
- Ensure viewport/accessibility parity (no zoom lock, responsive safe area).
- Verify back-navigation behavior from embedded Hypno to shell.
- Add shell-level health checks for required Hypno files.

### Package D - Cross-Module Shell Hardening
- Build module diagnostics section (module readiness + missing files list).
- Add unified local cleanup actions by module.
- Add one-click “recheck app state” action for troubleshooting.

### Package E - Pre-Visual Release Checklist
- Smoke test matrix (mobile + desktop): open/close, navigation, persistence, update.
- PWA install/update/offline sanity checks.
- Data safety checks (scoped localStorage cleanup only).

## Verification Rules (for each package)
- Run targeted lint checks on edited files.
- Run focused content checks (search for leftover placeholders/English strings).
- Validate changed behavior manually where runtime-only behavior is involved.
- Commit only after evidence checks pass.

## Exit Criteria
- Planner and Hypno Hebrew integrations are stable from shell perspective.
- Shell has diagnostics + cleanup utilities for non-technical troubleshooting.
- Remaining blocker list is only visual card assets (Archetypes fronts).

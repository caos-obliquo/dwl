# dwl patches (this fork)

Apply with `patch -p1 < patches/<name>.patch` from the repo root, then `make`.

| Patch | Applies to | Purpose | Source |
|---|---|---|---|
| `client-opacity.patch` | `dwl.c`, `config.def.h` | Per-client opacity + `Super+O` / `Super+Shift+O` bindings. Applied in-tree already. | dwl-patches `client-opacity` |
| `fix-rendermon-pending-resize-freeze.patch` | `dwl.c` | Fixes output freeze after layout/float toggles (dwl #1203, upstream PR !1208). Applied in-tree. | This fork |

## Notes

- `git diff` on a feature branch regenerates a patch. Keep each patch in sync
  with the applied tree so `git apply --check` stays green.
- Drop `fix-rendermon-pending-resize-freeze.patch` once upstream merges !1208
  and the fork rebases — the fix becomes part of the baseline.
- Full rationale in `docs/BUG-FLOAT-TILE-FREEZE.md`; other patch suggestions in
  `docs/PATCHES.md`.

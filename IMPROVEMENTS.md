# Improvement progress

Target: 100 independently reviewable improvements. Completed in this batch: 13. The target is not complete. Test cases and formatting edits are not counted separately.

1. Interval unit parsing rejects overflowing day/hour multipliers.
2. Range expansion terminates at i64::MAX without overflow.
3. Zero-width interval expansion returns no intervals.
4. Interval flooring avoids overflow at i64::MIN.
5. Zero-width flooring avoids division by zero.
6. Merging discards reversed and empty intervals.
7. Daily partition expansion terminates at the maximum representable date.
8. Default daily upper bounds avoid date overflow.
9. Daily declarations reject end dates before start dates.
10. Daily declarations reject duplicate start/end fields.
11. Multi declarations reject duplicate dimension names.
12. Static declarations reject duplicate partition keys.
13. Static keys reject the reserved multi-dimension separator.

## Validation

Locked workspace tests passed, including interval/partition regressions. The affected orch_common crate passes Clippy with existing warnings. Workspace Clippy fails in existing orch_core FFI raw-pointer APIs; these APIs were not changed.

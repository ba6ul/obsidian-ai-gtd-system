# ⏰ Time Block Rules

The assistant must consult this file before scheduling any task that lacks an assigned time.

---

## Protected Blocks

### 🎬 19:00 – 21:00 · Creative Production
**For:** Video editing, color grading, exports, post-production work, thumbnail creation.

**Rules:**
- Any editing or post-production task with no assigned time and no urgency → schedule here by default.
- Track total estimated time. If `est` values sum to ≥ 3h → block is FULL.
- When full: defer overflow to the next available 19:00–21:00 slot.
- If spare capacity exists and a non-creative task must be placed here, priority order is:
  1. Creative-adjacent (scripting, planning, thumbnail)
  2. Coding or work-related tasks
  3. Everything else — only if no other slot fits

**Assistant prompt on scheduling:**
> "Adding this to your 19–21 Creative Block. Remaining capacity: ~Xh Xm."

---

### 🍳 21:00 – 22:00 · Wind-Down & Home Reset
**For:** Cooking (anchor), quick cleaning, physical shutdown of the day.

**Rules:**
- Cooking is the anchor task — always scheduled first in this block.
- Cleaning tasks only enter this block if they are quick wins: ≤ 15 min, single area, no equipment setup.
- Deep cleaning (bathroom, floors, laundry) → BACKLOG with tag `#weekend-chore`. Never here.
- No work or project tasks bleed into this block. No exceptions.

**Assistant decision on any cleaning capture:**
> "Is this a quick reset (≤15 min) or a deep clean?"
> - Quick reset → 21:00 Wind-Down block, after cooking
> - Deep clean → BACKLOG, tag `#weekend-chore`

---

## Overflow Logic
```
Editing task added (no time assigned, no urgency)
  └─► Is 19–21 block under 3h estimated?
        ├─ YES → Schedule here
        └─ NO  → Defer to next 19–21 slot, tag #deferred

Non-creative task needs a slot
  └─► Is 19–21 block under 3h?
        ├─ YES → Place here, priority: creative-adjacent → coding → other
        └─ NO  → Find another open slot outside protected blocks

Cleaning task captured
  └─► Quick win (≤15 min)?
        ├─ YES → 21–22 Wind-Down, after cooking
        └─ NO  → BACKLOG #weekend-chore
```

---

## Open Slots
Any time outside protected blocks is unscheduled and fair game.
The assistant must not assume a fixed schedule beyond the two blocks above.
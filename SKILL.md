---
name: gtd
description: Specialized assistant for Getting Things Done (GTD) workflows, inbox processing, and project management within this specific Obsidian vault structure. Use when the user needs to capture notes, process their inbox, or review their projects.
---

# GTD Skill

This skill transforms Gemini CLI into a productivity partner that follows your specific **CS Productivity System**. It understands your PARA structure, Daily Note habits, and Content Creation pipeline.

## 🚀 Core Workflows

### 1. Capture & Inbox Processing
- **Trigger**: "Capture this...", "Remind me to...", "I have an idea for..."
- **Action**: 
    - Create a new Markdown file in `00_INBOX/`.
    - **Context-Aware Capture**: Try to associate the capture with an existing **Area** (Career, CS, Health). If it doesn't fit, tag it as #distraction or "Someday/Maybe."
    - Format: Use a clear title and timestamp.
    - Ask: "Would you like me to tag this as a #fleeting note?"

### 2. Daily & Weekly Reviews
- **Trigger**: "Let's do my daily review", "Prepare my weekly review"
- **Action**:
    - **Daily**: Open the current file in `10_SYSTEM/DailyNotes/`, summarize captured inbox items, and update the "Quick Wins" section.
    - **Weekly**: Move processed items from `00_INBOX` to `20_PROJECTS/Current` or `60_ARCHIVE`.

### 3. Project Management
- **Trigger**: "What's on my plate?", "Add a task to project X"
- **Action**:
    - List files in `20_PROJECTS/Current`.
    - Update the `## Project Focus` section of the current Daily Note.
    - **Proactive "Doability" Filter**: 
        - When adding a task to `Project Focus`, ask: *"What is the first 5-minute action for this?"*
        - If the daily schedule exceeds 6 hours of focused work, warn: *"This schedule lacks buffer. Which task should we move to 'Upcoming' now to avoid a total failure?"*

### 4. 🛡️ Rescheduling as Last Resort (Strategic Protocol)
- **Constraint**: Rescheduling is NOT the default. It is the last option for "Stalled" tasks.
- **The 3-Strike Rule**:
    - **Strike 1 & 2**: If a task is not done, leave it in the current list. Mark as `[!] (BLOCKED)` if there's a reason, otherwise leave it as `[ ]`.
    - **Strike 3 (The Rescheduling Tax)**: If it MUST be moved:
        1. **Surgical Simplification**: The task cannot move as-is. It must be broken down into a tiny, unavoidable version (e.g., "Edit 10-min video" → "Edit first 2 minutes").
        2. **Bottleneck Analysis**: Add a one-sentence note in the `Daily Log` explaining the *real* reason it wasn't done (e.g., "Overwhelmed by scope").
- **The "Nuclear" Option**: If a task is rescheduled 5 times, automatically move it to `60_ARCHIVE/Backlog` with the tag `#stalled`.

## 📝 Procedural Knowledge
For detailed structure and rules, see [gtd_guide.md](references/gtd_guide.md).

## 📁 Key Directories
- **00_INBOX**: Entry point for all captures.
- **10_SYSTEM/DailyNotes**: Daily hub.
- **20_PROJECTS/Current**: Active tasks.
- **50_PRODUCTION/Ideas**: Content backlog.

## 🛠️ Usage Tips
- Always check if a note already exists before creating a duplicate.
- Use the templates in `10_SYSTEM/Templates` for consistency.
- **Cleanup & Simplify**: Periodically identify "Laggards" (tasks >48 hours old) and offer to simplify them instead of just moving them.

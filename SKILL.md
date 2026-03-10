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

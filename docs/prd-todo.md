# Product Requirements Document (PRD) - Todo App Upgrade

## 1. Overview

We are upgrading the basic TODO app to support due dates, priorities, and filters so users can better organize and manage their tasks. The goal is to make the app more useful while keeping it simple and teachable, with no backend changes for the MVP.

---

## 2. MVP Scope

- Add an optional `dueDate` field to each task (ISO `YYYY-MM-DD` format)
- Add a `priority` field with three levels: `P1`, `P2`, `P3` (default: `P3`)
- Implement filters for task views: **All**, **Today**, **Overdue**
- Store all data locally (no backend or external storage)

---

## 3. Post-MVP Scope

- Visually highlight overdue tasks (e.g., red highlight)
- Add color-coded badges for priorities (red for P1, orange for P2, gray for P3)
- Implement sorting: overdue tasks first, then by priority (P1→P3), then by due date (ascending), undated tasks last

---

## 4. Out of Scope

- Notifications
- Any backend or external storage

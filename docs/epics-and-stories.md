

# MVP Requirements

- Epic: Task Due Dates
  - Story: Add due date field to task model
    - Technical Requirements:
      - Update the task data model to include an optional `dueDate` property (ISO `YYYY-MM-DD` format)
      - Ensure backward compatibility for tasks without a due date
  - Story: Display due date in task list
    - Technical Requirements:
      - Render the due date in the task list UI for tasks that have a due date
      - Hide or omit the due date field for tasks without a due date

- Epic: Task Prioritization
  - Story: Add priority field to task model
    - Technical Requirements:
      - Update the task data model to include a `priority` property (`P1`, `P2`, `P3`), defaulting to `P3`
      - Ensure all new tasks have a priority assigned
  - Story: Display priority in task list
    - Technical Requirements:
      - Show the priority value in the task list UI as a label or badge
      - Visually distinguish each priority level

- Epic: Task Filtering
  - Story: Add filter for all tasks
    - Technical Requirements:
      - Implement a filter/view to display all tasks
  - Story: Add filter for today’s tasks
    - Technical Requirements:
      - Implement a filter/view to display only tasks with a due date matching today’s date
      - Exclude tasks without a due date from this view
  - Story: Add filter for overdue tasks
    - Technical Requirements:
      - Implement a filter/view to display only tasks with a due date before today and not completed
      - Exclude completed tasks from the overdue view

- Epic: Local Data Storage
  - Story: Store tasks locally on device
    - Technical Requirements:
      - Use browser storage (localStorage or IndexedDB) to persist all task data
      - Ensure tasks persist after page reload
      - Do not use any backend or external storage

# Post-MVP Requirements

- Epic: Overdue Task Highlighting
  - Story: Visually highlight overdue tasks
    - Technical Requirements:
      - Apply a visual style (e.g., red highlight or border) to overdue tasks in the UI
      - Only highlight tasks with a due date before today and not completed

- Epic: Priority Badges
  - Story: Add color-coded badges for priorities
    - Technical Requirements:
      - Display a red badge for P1, orange for P2, and gray for P3 in the task list

- Epic: Task Sorting
  - Story: Sort tasks by overdue status
    - Technical Requirements:
      - Ensure overdue tasks are listed at the top of the task list
  - Story: Sort tasks by priority
    - Technical Requirements:
      - Within each group (overdue, not overdue), sort tasks by priority (P1 first, then P2, then P3)
  - Story: Sort tasks by due date
    - Technical Requirements:
      - Within each priority, sort tasks by due date in ascending order
  - Story: Sort undated tasks last
    - Technical Requirements:
      - Tasks without a due date appear after all dated tasks in their group

# Post-MVP Requirements

- Epic: Overdue Task Highlighting
  - Story: Visually highlight overdue tasks
- Epic: Priority Badges
  - Story: Add color-coded badges for priorities
- Epic: Task Sorting
  - Story: Sort tasks by overdue status
  - Story: Sort tasks by priority
  - Story: Sort tasks by due date
  - Story: Sort undated tasks last
    - Tasks without a due date appear after all dated tasks in their group
  - Technical Requirements: _TBD_

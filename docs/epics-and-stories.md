
## MVP Requirements

Epic: Add Due Date to Tasks
	- Story: Add due date field to task model
		- Acceptance Criteria:
			- Task model includes optional dueDate (YYYY-MM-DD)
			- Existing tasks remain valid without dueDate
	- Story: Display due date in task list
		- Acceptance Criteria:
			- Due date shown for tasks with dueDate
			- No due date shown if not set
	- Story: Allow user to set or edit due date
		- Acceptance Criteria:
			- User can add or change due date when creating/editing a task
			- Input uses date picker or valid date field

Epic: Add Priority to Tasks
	- Story: Add priority field to task model
		- Acceptance Criteria:
			- Task model includes priority (P1, P2, P3; default P3)
			- Existing tasks default to P3
	- Story: Display priority in task list
		- Acceptance Criteria:
			- Priority shown for each task
			- P1, P2, or P3 label visible
	- Story: Allow user to set or edit priority
		- Acceptance Criteria:
			- User can select priority when creating/editing a task
			- Priority defaults to P3 if not set

Epic: Implement Task Filters
	- Story: Add filter for All tasks
		- Acceptance Criteria:
			- All tasks shown when All filter is active
	- Story: Add filter for Today’s tasks
		- Acceptance Criteria:
			- Only tasks due today are shown
			- Uses current date for filtering
	- Story: Add filter for Overdue tasks
		- Acceptance Criteria:
			- Only tasks with dueDate before today are shown
			- Excludes completed or undated tasks

Epic: Local Data Storage
	- Story: Store tasks locally in browser
		- Acceptance Criteria:
			- All task data saved in local storage
			- No backend or external storage used
	- Story: Persist due date and priority fields
		- Acceptance Criteria:
			- Due date and priority persist after reload
			- Changes reflected in local storage

## Post-MVP Requirements

Epic: Visual Highlight for Overdue Tasks
	- Story: Highlight overdue tasks in red
		- Acceptance Criteria:
			- Overdue tasks visually distinct (e.g., red highlight)
			- Only overdue tasks are highlighted

Epic: Priority Badges
	- Story: Add color-coded badges for priorities
		- Acceptance Criteria:
			- P1 badge is red, P2 is orange, P3 is gray
			- Badge color matches priority

Epic: Advanced Sorting
	- Story: Sort tasks by overdue status
		- Acceptance Criteria:
			- Overdue tasks appear first in list
	- Story: Sort tasks by priority
		- Acceptance Criteria:
			- Within overdue/non-overdue, P1 before P2, P2 before P3
	- Story: Sort tasks by due date
		- Acceptance Criteria:
			- Within same priority, earlier due dates appear first
	- Story: Place undated tasks last
		- Acceptance Criteria:
			- Tasks without dueDate always at end of list


## MVP Requirements

Epic: Add Due Date to Tasks
	- Story: Add due date field to task model
		- Acceptance Criteria:
			- Task model includes optional dueDate (YYYY-MM-DD)
			- Existing tasks remain valid without dueDate
		- Technical Requirements:
			- Add `due_date` column to backend `tasks` table (already present)
			- Accept and store `due_date` in backend API (POST/PUT)
			- Add `dueDate` state and field in TaskForm.js
			- Ensure due date is passed to backend on save
	- Story: Display due date in task list
		- Acceptance Criteria:
			- Due date shown for tasks with dueDate
			- No due date shown if not set
		- Technical Requirements:
			- Render due date in TaskList.js using formatDueDate
			- Show due date chip only if present
	- Story: Allow user to set or edit due date
		- Acceptance Criteria:
			- User can add or change due date when creating/editing a task
			- Input uses date picker or valid date field
		- Technical Requirements:
			- Use type="date" input in TaskForm.js
			- Update dueDate state on change
			- Pass dueDate to onSave handler

Epic: Add Priority to Tasks
	- Story: Add priority field to task model
		- Acceptance Criteria:
			- Task model includes priority (P1, P2, P3; default P3)
			- Existing tasks default to P3
		- Technical Requirements:
			- Add `priority` field to frontend task model (TaskForm.js, TaskList.js)
			- Add priority input (dropdown/select) in TaskForm.js
			- Default priority to P3 if not set
			- Pass priority to backend API (future, not in current backend)
	- Story: Display priority in task list
		- Acceptance Criteria:
			- Priority shown for each task
			- P1, P2, or P3 label visible
		- Technical Requirements:
			- Render priority label or badge in TaskList.js
	- Story: Allow user to set or edit priority
		- Acceptance Criteria:
			- User can select priority when creating/editing a task
			- Priority defaults to P3 if not set
		- Technical Requirements:
			- Add select/dropdown for priority in TaskForm.js
			- Update priority state on change
			- Pass priority to onSave handler

Epic: Implement Task Filters
	- Story: Add filter for All tasks
		- Acceptance Criteria:
			- All tasks shown when All filter is active
		- Technical Requirements:
			- Implement filter UI in frontend (App.js or TaskList.js)
			- Show all tasks from API
	- Story: Add filter for Today’s tasks
		- Acceptance Criteria:
			- Only tasks due today are shown
			- Uses current date for filtering
		- Technical Requirements:
			- Filter tasks in frontend by comparing due_date to today
	- Story: Add filter for Overdue tasks
		- Acceptance Criteria:
			- Only tasks with dueDate before today are shown
			- Excludes completed or undated tasks
		- Technical Requirements:
			- Filter tasks in frontend by due_date < today
			- Exclude tasks without due_date

Epic: Local Data Storage
	- Story: Store tasks locally in browser
		- Acceptance Criteria:
			- All task data saved in local storage
			- No backend or external storage used
		- Technical Requirements:
			- Use localStorage API in frontend to persist tasks
			- Read from localStorage on app load
	- Story: Persist due date and priority fields
		- Acceptance Criteria:
			- Due date and priority persist after reload
			- Changes reflected in local storage
		- Technical Requirements:
			- Save due_date and priority fields in localStorage
			- Update localStorage on task add/edit/delete

## Post-MVP Requirements

Epic: Visual Highlight for Overdue Tasks
	- Story: Highlight overdue tasks in red
		- Acceptance Criteria:
			- Overdue tasks visually distinct (e.g., red highlight)
			- Only overdue tasks are highlighted
		- Technical Requirements:
			- Add conditional styling in TaskList.js for overdue tasks
			- Use red background or text for overdue items

Epic: Priority Badges
	- Story: Add color-coded badges for priorities
		- Acceptance Criteria:
			- P1 badge is red, P2 is orange, P3 is gray
			- Badge color matches priority
		- Technical Requirements:
			- Render badge in TaskList.js with color based on priority

Epic: Advanced Sorting
	- Story: Sort tasks by overdue status
		- Acceptance Criteria:
			- Overdue tasks appear first in list
		- Technical Requirements:
			- Sort tasks array in frontend by overdue status
	- Story: Sort tasks by priority
		- Acceptance Criteria:
			- Within overdue/non-overdue, P1 before P2, P2 before P3
		- Technical Requirements:
			- Sort tasks array in frontend by priority value
	- Story: Sort tasks by due date
		- Acceptance Criteria:
			- Within same priority, earlier due dates appear first
		- Technical Requirements:
			- Sort tasks array in frontend by due_date ascending
	- Story: Place undated tasks last
		- Acceptance Criteria:
			- Tasks without dueDate always at end of list
		- Technical Requirements:
			- Sort tasks so tasks with no due_date are last

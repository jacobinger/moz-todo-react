# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev      # Start dev server with HMR at http://localhost:5173
npm run build    # Production build to dist/
npm run preview  # Preview production build locally
npm run lint     # Run ESLint
```

There are no tests configured in this project.

## Architecture

This is the [MDN React Todo tutorial](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Frameworks_libraries/React_todo_list_beginning) app — a React 19 + Vite todo list called "TodoMatic".

**Data flow:** All task state (`tasks` array, `filter` string) lives in `App`. The initial task data is hardcoded in `src/main.jsx` and passed as `props.tasks`. State mutations (add/toggle/delete/edit) are defined in `App` and passed down as callback props.

**Key patterns:**
- `usePrevious` custom hook (defined in both `App.jsx` and `Todo.jsx`) captures the previous render's value via `useRef` — used for focus management after task deletion and edit mode toggling.
- `FILTER_MAP` in `App.jsx` maps filter names (`"All"`, `"Active"`, `"Completed"`) to predicate functions applied before rendering the task list.
- Task IDs are generated with `nanoid` prefixed as `todo-<id>`.
- Accessibility: `listHeadingRef` receives focus when a task is deleted; `editFieldRef`/`editButtonRef` manage focus when entering/exiting edit mode in `Todo`.

**Component responsibilities:**
- `App` — state management, filter logic, renders `Form`, `FilterButton` list, and filtered `Todo` list
- `Todo` — per-task view/edit toggle with two inline templates (`viewTemplate`/`editingTemplate`)
- `Form` — controlled input for adding new tasks
- `FilterButton` — uses `aria-pressed` to indicate active filter

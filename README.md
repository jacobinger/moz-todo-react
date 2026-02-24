# TodoMatic

A todo list app built by following the [MDN React tutorial](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Frameworks_libraries/React_todo_list_beginning). Built with React 19 and Vite.

**Live site:** https://nuwebdev.github.io/moz-todo-react/

## Tutorial steps

Each step of the tutorial is tagged in the commit history, making it easy to check out the code at any stage:

| Tag | Step |
|-----|------|
| `step-1` | React getting started — JSX and props demo |
| `step-2` | React ToDo list beginning — static app structure |
| `step-3` | Componentizing — extract Todo, Form, and FilterButton |
| `step-4` | React events and state — add/delete/toggle tasks |
| `step-5` | Editing, filtering, and conditional rendering |
| `step-6` | React accessibility — keyboard focus management |

```bash
git checkout step-3   # view the code at any step
git checkout main     # return to the latest version
```

## Features

- Add, edit, and delete tasks
- Filter tasks by All / Active / Completed
- Keyboard focus management for accessibility

## Development

```bash
npm install
npm run dev
```

## Deploying to GitHub Pages

```bash
npm run deploy
```

This builds the app and publishes the `dist/` folder to the `gh-pages` branch.

**First-time setup:** In the GitHub repository settings, go to **Pages** and set the source branch to `gh-pages`.

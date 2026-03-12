# Visual Studio Code Guide

### A Complete Introduction for Absolute Beginners

---

## What Is VS Code?

VS Code (Visual Studio Code) is a **free code editor** made by Microsoft. Think of it like Microsoft Word, but built specifically for writing code — with superpowers.

It's not just a place to type. VS Code understands your code: it highlights syntax, catches errors as you type, helps you navigate large projects, runs your code, integrates with Git, and can be extended to do almost anything.

It's the most popular code editor in the world, used by beginners and senior engineers alike.

---

## Why VS Code?

- Works on Mac, Windows, and Linux — for free
- Works with every major language: Python, JavaScript, HTML, SQL, and more
- Built-in terminal — no need to switch windows
- Built-in Git support
- Thousands of extensions to add any feature you need

---

## Part 1 — Installing VS Code

1. Go to [code.visualstudio.com](https://code.visualstudio.com)
2. Click the big **Download** button (it auto-detects your OS)
3. Run the installer and follow the prompts

**On Mac:** drag the app to your Applications folder.
**On Windows:** check "Add to PATH" during installation — this lets you open VS Code from the terminal.

To verify it's installed, open your terminal and run:

```bash
code --version
```

---

## Part 2 — The Interface

When you first open VS Code, here's what you're looking at:

### The Activity Bar (left side icons)

The vertical bar on the far left gives you access to your main panels:

| Icon           | What it is                             |
| -------------- | -------------------------------------- |
| Explorer       | Your project files and folders         |
| Search         | Find and replace text across all files |
| Source Control | Git integration                        |
| Run & Debug    | Run and debug your code                |
| Extensions     | Browse and install extensions          |

### The Editor Area

This is where your files open. You can have multiple files open as **tabs**, and split the editor into side-by-side panes by right-clicking a tab and choosing "Split Right."

### The Terminal Panel

A full terminal, built right into VS Code. Toggle it with Ctrl+backtick on Mac and Windows/Linux, or go to **View → Terminal**. It automatically opens in your project folder.

---

## Part 3 — Opening a Project

VS Code works best when you open an entire **folder**, not just individual files. This gives it full context about your project.

**From the menu:** File → Open Folder → select your project folder

**From the terminal (fastest method):**

```bash
cd my-project
code .
```

The `.` means "open the current folder in VS Code." Once you start using this, you'll never stop.

---

## Part 4 — Essential Keyboard Shortcuts

Learning even a handful of shortcuts will dramatically speed up your work.

### Must-Know Shortcuts

| Action                 | Mac                 | Windows/Linux    |
| ---------------------- | ------------------- | ---------------- |
| Command Palette        | `Cmd+Shift+P`       | `Ctrl+Shift+P`   |
| Quick file open        | `Cmd+P`             | `Ctrl+P`         |
| Save file              | `Cmd+S`             | `Ctrl+S`         |
| Find in current file   | `Cmd+F`             | `Ctrl+F`         |
| Find across all files  | `Cmd+Shift+F`       | `Ctrl+Shift+F`   |
| Toggle terminal        | `Ctrl+backtick`     | `Ctrl+backtick`  |
| Duplicate a line       | `Shift+Option+Down` | `Shift+Alt+Down` |
| Move a line up/down    | `Option+Up/Down`    | `Alt+Up/Down`    |
| Comment/uncomment line | `Cmd+/`             | `Ctrl+/`         |
| Go to line number      | `Ctrl+G`            | `Ctrl+G`         |
| Open Settings          | `Cmd+,`             | `Ctrl+,`         |

### The Command Palette — Your Most Important Shortcut

`Cmd+Shift+P` (Mac) or `Ctrl+Shift+P` (Windows) opens a search bar where you can find and run **any** VS Code command by typing its name. You don't need to memorize every menu location — just open the palette and type what you want.

Examples:

- `"format document"` — auto-formats your code
- `"rename symbol"` — rename a variable everywhere it appears
- `"toggle word wrap"` — wrap long lines
- `"change color theme"` — switch your theme

When in doubt, open the Command Palette.

---

## Part 5 — Extensions

Extensions are add-ons that give VS Code new powers. There are thousands of them, and most are free.

### Installing an Extension

1. Click the **Extensions icon** in the Activity Bar (or press `Cmd+Shift+X`)
2. Type the extension name in the search bar
3. Click **Install**

### Recommended Extensions for Beginners

**For everyone:**

- **Prettier** — automatically formats your code to look clean and consistent on every save
- **GitLens** — supercharges Git; shows who wrote each line and when
- **Error Lens** — displays error messages inline, right next to the problem line

**For Python:**

- **Python** (by Microsoft) — essential; adds linting, debugging, and IntelliSense
- **Pylance** — fast, smart Python language support

**For web development:**

- **Live Server** — launches a local server that auto-reloads when you save HTML/CSS

**For writing:**

- **Markdown Preview Enhanced** — renders Markdown in a side panel as you type

---

## Part 6 — IntelliSense (Smart Autocomplete)

IntelliSense is VS Code's smart autocomplete system. As you type, it suggests:

- Variable and function names you've already defined
- Methods available on an object (type `mylist.` and see all list methods)
- Function parameters and what they expect
- Documentation snippets

It activates automatically as you type. You can also trigger it manually with `Ctrl+Space`.

When a suggestion pops up, press `Tab` or `Enter` to accept it.

---

## Part 7 — Find and Replace

### In the current file

`Cmd+F` (Mac) / `Ctrl+F` (Windows) — opens a search bar in the top-right corner of the editor

### Across your entire project

`Cmd+Shift+F` (Mac) / `Ctrl+Shift+F` (Windows) — searches every file in your folder at once

Both support **case-sensitive search** and **regular expressions** for advanced pattern matching.

### Rename a symbol everywhere

For renaming variables or functions throughout your codebase: click on the name, then press `F2`. Type the new name and press Enter — VS Code updates every occurrence.

---

## Part 8 — The Integrated Terminal

The terminal inside VS Code is a full terminal — the same as opening Terminal or Command Prompt separately. The big benefit: it opens directly in your project folder.

**Open/close the terminal:** `Ctrl+backtick`

**Open multiple terminals:** click the `+` button in the terminal panel. Useful for running a server in one while doing other commands in another.

**Split the terminal:** click the split icon to have two terminals side by side.

---

## Part 9 — Settings and Customization

Open Settings with `Cmd+,` (Mac) / `Ctrl+,` (Windows). Settings has a search bar — just type what you're looking for.

### Useful settings to change early on

| Setting            | What to set it to                 | Why                                       |
| ------------------ | --------------------------------- | ----------------------------------------- |
| **Auto Save**      | `afterDelay`                      | Never lose unsaved work                   |
| **Format On Save** | `true`                            | Auto-formats code every time you save     |
| **Word Wrap**      | `on`                              | Prevents long lines from going off-screen |
| **Font Size**      | Your preference (14–16 is common) | Comfort                                   |
| **Tab Size**       | `4` for Python, `2` for JS/HTML   | Language conventions                      |

### Themes

Change VS Code's colors under **File → Preferences → Color Theme**, or search "theme" in the Command Palette.

Popular themes: **One Dark Pro**, **Dracula**, **GitHub Dark**, **Tokyo Night**

---

## Part 10 — Built-in Git Integration

VS Code has Git built right in. Click the **Source Control icon** in the Activity Bar (the branch icon):

- Files you've changed are listed automatically
- Click any file to see a **diff** — what you changed, highlighted in green (added) and red (removed)
- Click `+` next to a file to stage it
- Type your commit message in the box at the top
- Click the checkmark to commit

This is a visual alternative to running `git add` and `git commit` in the terminal. Both approaches work — use whichever feels more comfortable.

---

## Quick Reference Cheat Sheet

```
Opening things
  code .                     open current folder in VS Code
  Cmd/Ctrl+P                 quick-open any file by name
  Cmd/Ctrl+Shift+P           command palette

Editing
  Cmd/Ctrl+S                 save
  Cmd/Ctrl+Z                 undo
  Cmd/Ctrl+/                 toggle line comment
  Alt/Option+Up/Down         move line up or down
  Shift+Alt/Option+Down      duplicate line
  F2                         rename symbol everywhere

Navigation
  Cmd/Ctrl+F                 find in file
  Cmd/Ctrl+Shift+F           find across project
  Ctrl+G                     go to line number
  Ctrl+Space                 trigger IntelliSense

Terminal
  Ctrl+backtick              toggle terminal

Extensions
  Cmd/Ctrl+Shift+X           open extensions panel
```

---

## Common Mistakes to Avoid

| Mistake                                      | Fix                                                            |
| -------------------------------------------- | -------------------------------------------------------------- |
| Opening individual files instead of a folder | Use `code .` or File → Open Folder                             |
| Not using the Command Palette                | `Cmd+Shift+P` finds any feature instantly                      |
| Ignoring red underlines                      | They're errors — hover over them to read the message           |
| Installing too many extensions at once       | Start with the essentials; add more as you need them           |
| Skipping Format On Save                      | Turn it on — consistent formatting prevents a lot of headaches |

---

## Where to Learn More

- **[code.visualstudio.com/docs](https://code.visualstudio.com/docs)** — Official, beginner-friendly documentation
- **[VS Code Intro Videos](https://code.visualstudio.com/docs/getstarted/introvideos)** — Short official video tutorials
- Command Palette → search `"keyboard shortcuts"` → opens a printable shortcut reference for your OS

---

## You're Ready

VS Code rewards exploration. The more shortcuts you learn and the more you poke around the Command Palette, the faster you'll work. Start with `Cmd+P`, `Cmd+Shift+P`, and the integrated terminal — and build from there.

# VSCodeVim-configs
VSCodeVim is a Vim emulator for Visual Studio Code

# settings.json
```
  "vim.easymotion": true,
  "vim.incsearch": true,
  "vim.useSystemClipboard": true,
  "vim.useCtrlKeys": true,
  "vim.hlsearch": true,
  "vim.highlightedyank.enable": true,
  "vim.highlightedyank.duration": 30,
  // To improve performance"
  "extensions.experimental.affinity": {
    "vscodevim.vim": 1
  },
  "vim.leader": "<space>",
  "vim.handleKeys": {
    "<C-a>": false,
    "<C-f>": false,
    "<C-w>": false
  },
  // Vim Statusbar Colors
  "vim.statusBarColorControl": true,
  "vim.statusBarColors.normal": "#000000",
  "vim.statusBarColors.insert": "#5C5470",
  "vim.statusBarColors.visual": "#183D3D",
  "vim.statusBarColors.visualline": "#183D3D",
  "vim.statusBarColors.visualblock": "#183D3D",
  "vim.statusBarColors.replace": "#B9B4C7",
  "vim.statusBarColors.commandlineinprogress": "#597F6F",
  "vim.statusBarColors.searchinprogressmode": "#3D5F6A",
  "vim.statusBarColors.easymotionmode": "#1F6E8C",
  "vim.statusBarColors.easymotioninputmode": "#1F6E8C",
```

### Normal Mode

| Command       | Description                   |
| ------------- | ----------------------------- |
| `<leader>` o  | Open/Close Sidebar            |
| `<leader>` e  | Focus File Tree               |
| `<leader>` x  | Open Extensions               |
| `<leader>` g  | Open Source Control           |
| `<leader>` ff | Find File                     |
| `<leader>` fc | Format Code                   |
| `<leader>` fo | Open Folder                   |
| `escape`      | Clear Highlight               |
| `u`           | System undo                   |
| `ctrl+u`      | Scroll Up and Center          |
| `ctrl+d`      | Scroll Down and Center        |
| `n`           | Center Next Search Result     |
| `N`           | Center Previous Search Result |
| `:`           | Open Command Palette          |

<br>
<details>
 <summary>settings.json (click to expand)</summary>


```json
  "vim.normalModeKeyBindingsNonRecursive": [
    // Open/Close Sidebar
    {
      "before": ["<Leader>", "o"],
      "commands": ["workbench.action.toggleSidebarVisibility"]
    },
    // Focus File Tree
    {
      "before": ["<Leader>", "e"],
      "commands": ["workbench.explorer.fileView.focus"]
    },
    // Open Folder
    {
      "before": ["<Leader>", "f", "o"],
      "commands": ["workbench.action.files.openFolderViaWorkspace"]
    },
    // Find File
    {
      "before": ["<Leader>", "f", "f"],
      "commands": ["workbench.action.quickOpen"]
    },
    // Open Extensions
    {
      "before": ["<Leader>", "x"],
      "commands": ["workbench.view.extensions"]
    },
    // Open Source Control
    {
      "before": ["<Leader>", "g"],
      "commands": ["workbench.view.scm"]
    },
    // Format Code
    {
      "before": ["<Leader>", "f", "c"],
      "commands": ["editor.action.formatDocument"],
      "silent": true
    },
    // Clear Highlight
    {
      "before": ["escape"],
      "commands": [":nohl"],
      "silent": true
    },
    // System undo
    {
      "before": ["u"],
      "commands": ["undo"]
    },
    // Scroll and Center
    {
      "before": ["ctrl+u"],
      "after": ["ctrl+u", "z", "z"]
    },
    {
      "before": ["ctrl+d"],
      "after": ["ctrl+d", "z", "z"]
    },
    // Center on Search
    {
      "before": ["n"],
      "after": ["n", "z", "z"]
    },
    {
      "before": ["N"],
      "after": ["N", "z", "z"]
    }
  ],
```

</details>
<br>
<br>

### Visual Mode

| Command       | Description                   |
| ------------- | ----------------------------- |
| `p`           | paste without overriding the current register                   |

<br>
<details>
 <summary>settings.json (click to expand)</summary>

```json
  "vim.visualModeKeyBindingsNonRecursive": [
    // paste without overriding the current register
    {
      "before": ["p"],
      "after": ["p", "g", "v", "y"]
    }
  ],
```

</details>
<br>
<br>

# keybindings.json

| Command    | Description                    |
| ---------- | ------------------------------ |
| `space` e  | Focus File Tree                |
| `r`        | File Tree Focus: Rename        |
| `a`        | File Tree Focus: New File      |
| `d`        | File Tree Focus: Delete File   |
| `x`        | File Tree Focus: Cut File      |
| `p`        | File Tree Focus: Paste         |
| `y`        | File Tree Focus: Copy          |
| `escape`   | Sidebar Focus: Go Back to File |
| `space` fo | Open Folder                    |
| `space` ff | Find File                      |
| `space` x  | Open Extensions                |
| `space` g  | Open Source Control            |
| `          | Open/Close Terminal            |
| `ctrl+r`   | System Redo                    |

<br>
<details>
 <summary>keybindings.json (click to expand)</summary>
  
```json
  // Focus File Tree
  {
    "key": "space e",
    "command": "workbench.files.action.focusFilesExplorer",
    "when": "!workbench.files.action.focusFilesExplorer && !inputFocus"
  },
  // File Tree Motions
  {
    "key": "r",
    "command": "renameFile",
    "when": "filesExplorerFocus && foldersViewVisible && !explorerResourceIsRoot && !explorerResourceReadonly && !inputFocus"
  },
  {
    "key": "a",
    "command": "explorer.newFile",
    "when": "filesExplorerFocus && !inputFocus"
  },
  {
    "key": "d",
    "command": "deleteFile",
    "when": "filesExplorerFocus && !inputFocus"
  },
  {
    "key": "x",
    "command": "filesExplorer.cut",
    "when": "filesExplorerFocus && !inputFocus"
  },
  {
    "key": "p",
    "command": "filesExplorer.paste",
    "when": "filesExplorerFocus && !inputFocus"
  },
  {
    "key": "y",
    "command": "filesExplorer.copy",
    "when": "filesExplorerFocus && !inputFocus"
  },
  // Go Back to File From Sidebar
  {
    "key": "escape",
    "command": "workbench.action.focusActiveEditorGroup",
    "when": "sideBarFocus"
  },
  // Open Folder
  {
    "key": "space f o",
    "command": "workbench.action.files.openFolderViaWorkspace",
    "when": "!inputFocus"
  },
  // Find File
  {
    "key": "space f f",
    "command": "workbench.action.quickOpen",
    "when": "!inputFocus"
  },
  // Open/Close Terminal
  {
    "key": "`",
    "command": "workbench.action.terminal.toggleTerminal",
    "when": "terminal.active && vim.mode != 'Insert'"
  },
  // Open Extensions
  {
    "key": "space x",
    "command": "workbench.view.extensions",
    "when": "!inputFocus"
  },
  // Open Source Control
  {
    "key": "space g",
    "command": "workbench.view.scm",
    "when": "!inputFocus"
  },
  // System Redo
  {
    "key": "ctrl+r",
    "command": "redo"
  }
```

</details>
<br>
<br>

# VSCodeVim-configs
VSCodeVim is a Vim emulator for Visual Studio Code

# Vim settings
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
```
# Shortcuts

### Normal Mode

| Command       | Description                   |
| ------------- | ----------------------------- |
| `<leader>` o  | Open/Close Sidebar            |
| `<leader>` e  | Focus File Tree               |
| `<leader>` of | Open Folder                   |
| `<leader>` ff | Find File                     |
| `<leader>` x  | Open Extensions               |
| `<leader>` g  | Open Source Control           |
| `<leader>` fc | Format Code                   |
| `escape`      | Clear Highlight               |
| `u`           | System undo                   |
| `ctrl+u`      | Scroll Up and Center          |
| `ctrl+d`      | Scroll Down and Center        |
| `n`           | Center Next Search Result     |
| `N`           | Center Previous Search Result |

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
      "before": ["<Leader>", "o", "f"],
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

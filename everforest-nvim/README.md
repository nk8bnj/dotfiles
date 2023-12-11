# Everforest.nvim

A Lua port of the [everforest](https://github.com/sainnhe/everforest) colour
scheme.

![screenshot one](https://github.com/8bitnikita/everforest-nvim/raw/main/Screenshot%202023-04-15%20at%2013.15.49.png)
![screenshot two](https://github.com/8bitnikita/everforest-nvim/raw/main/Screenshot%202023-04-15%20at%2013.16.54.png)

## Installation

Using [lazy.nvim](https://github.com/folke/lazy.nvim):

```lua
require("lazy").setup({
  "8bitnikita/everforest-nvim",
  version = false,
  lazy = false,
  priority = 1000, -- make sure to load this before all the other start plugins
  -- Optional; default configuration will be used if setup isn't called.
  config = function()
    require("everforest").setup({
      -- Your config here
    })
  end,
})
```

Using [packer.nvim](https://github.com/wbthomason/packer.nvim):

```lua
use({
  "8bitnikita/everforest-nvim",
  -- Optional; default configuration will be used if setup isn't called.
  config = function()
    require("everforest").setup()
  end,
})
```

Using [vim-plug](https://github.com/junegunn/vim-plug):

```viml
Plug '8bitnikita/everforest-nvim', { 'branch': 'main' }
```

## Usage

```viml
" In VimL

" This has both light & dark modes to match your background setting.
colorscheme everforest
```

```lua
-- In Lua
vim.cmd([[colorscheme everforest]])

-- Alternatively
require("everforest").load()
```

To enable the everforest theme for LuaLine, you can specify it as such:

```lua
require("lualine").setup({
  options = {
    -- ... other configuration
    theme = "everforest", -- Can also be "auto" to detect automatically.
  }
})
```

## Configuration

> Configuration options aren't as comprehensive as the original everforest
> theme yet.

This colour scheme has a light and a dark mode which are configured using the
vim background setting: `:set background=light` or `vim.o.background=dark` as
appropriate.

This is the default config:

```lua
require("everforest").setup({
  -- Controls the "hardness" of the background. Options are "soft", "medium" or "hard".
  -- Default is "medium".
  background = "medium",
  -- How much of the background should be transparent. Options are 0, 1 or 2.
  -- Default is 0.
  --
  -- 2 will have more UI components be transparent (e.g. status line
  -- background).
  transparent_background_level = 0,
  -- Whether italics should be used for keywords, builtin types and more.
  italics = false,
  -- Disable italic fonts for comments. Comments are in italics by default, set
  -- this to `true` to make them _not_ italic!
  disable_italic_comments = false,
})
```

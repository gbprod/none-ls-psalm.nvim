# none-ls-psalm.nvim

Psalm diagnostic plugin for [none-ls.nvim](https://github.com/nvimtools/none-ls.nvim).

Since this diagnostic will be deprecated from [none-ls.nvim](https://github.com/nvimtools/none-ls.nvim)
(see [this issue](https://github.com/nvimtools/none-ls.nvim/issues/58)) because a LSP alternative is available,
this repository allows to keep using [psalm](https://psalm.dev) linter with none-ls.nvim.

**Note:** This plugin is not intended to be used alone, it is a dependency of none-ls.nvim.

## 📦 Installation

This should be used as a dependency of **none-ls.nvim**.

### [lazy.nvim](https://github.com/folke/lazy.nvim)

```lua
{
  {
    "nvimtools/none-ls.nvim",
    config = function()
        require("null-ls").register(require("none-ls-psalm.diagnostics"))
    end,
    dependencies = {
        "gbprod/none-ls-psalm.nvim",
    },
  },
}
```

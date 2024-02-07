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

## FAQ

How to trigger the formatter only if the project is using psalm?

```lua
null_ls.register(require("none-ls-psalm.diagnostics").with({
  condition = function(utils)
    return utils.root_has_file("psalm.xml")
  end,
}))
```

How to use project's psalm bin instead of globally installed one?

```lua
null_ls.register(require("none-ls-psalm.diagnostics").with({
  command = "vendor/bin/psalm",
  condition = function(utils)
    return utils.root_has_file("vendor/bin/psalm")
  end,
}))
```

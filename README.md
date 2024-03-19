# none-ls-psalm.nvim

Psalm diagnostic source for [none-ls.nvim](https://github.com/nvimtools/none-ls.nvim).

Since this diagnostic was deprecated from [none-ls.nvim](https://github.com/nvimtools/none-ls.nvim)
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
    dependencies = {
        "gbprod/none-ls-php.nvim",
    },
  },
}
```

## Setup

Follow the steps in null-ls [setup](https://github.com/nvimtools/none-ls.nvim?tab=readme-ov-file#setup) section.

```lua
local null_ls = require("null-ls")

null_ls.setup {
  sources = {
    require("none-ls-psalm.diagnostics"),
    ...
  }
}
```

## Related projects

You can search for sources via the [`none-ls-sources` topic](https://github.com/topics/none-ls-sources).

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

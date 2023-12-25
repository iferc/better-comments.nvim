# Better Comments - NVIM

Better comments adds pattern-based comment highlighting so that important comments are hard to miss.

## Prerequisites

- Treesiter ([nvim-treesitter/nvim-treesitter](https://github.com/nvim-treesitter/nvim-treesitter)) is required.

## Installation via [Lazy](https://github.com/folke/lazy.nvim)

```lua
require("lazy").setup({
    {
        'iferc/better-comments.nvim',
        dependencies = { { 'nvim-treesitter/nvim-treesitter' } },
        config = function()
            require('better-comments').setup({
                -- Begins with the word TODO or TO DO in any case.
                -- Examples:
                --   TODO, do the thing.
                --   @todo: thing must be done.
                --   To Do!
                -- Defaults to `true`.
                highlight_todo = true

                -- Begins with the word WARNING in any case.
                -- Examples:
                --   WARNING this next command must be executed.
                --   warning: other repositories rely on this next behaviour.
                -- Defaults to `true`.
                highlight_warning = true

                -- Begins with ticket IDs in any case, e.g. PRJ-123
                -- Examples:
                --   LIFE-42
                --   API-1337
                --   lazy-123
                --   WARNING-555
                -- Defaults to `true`.
                highlight_ticket_id = true

                -- Begins with exclamation point aka bang "!" to emphasize comment.
                -- This can be applied on top of earlier rules.
                -- Examples:
                --!  Important module notes...
                --  !BEWARE, there be dragons here.
                -- ! TODO, do the thing.
                --!  WARNING this next command must be executed.
                --  !LIFE-42
                -- Defaults to `true`.
                highlight_bang = true

                -- Custom patterns. Each pattern is applied in order
                -- and multiple patterns may compose together.
                -- Defaults to `empty table`.
                tags = {
                    {
                        pattern = "FIX",
                        fg = "white",
                        bg = "#f44747",
                        bold = true,
                        virtual_text = "This is virtual Text from FIX",
                    },
                }
            })
        end,
    },
})
```

## Future plans

- Virtual text using a closure given file, line, cols, and text.
- Pulling ticket status in a virtual text section of a ticket id comment.
- Research whether or not there is a way to tie colors to colorschemes/themes.

## License

[MIT](https://choosealicense.com/licenses/mit/)

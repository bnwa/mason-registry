# Mason Registry

This registry features packages for tooling not yet available in the [official
registry](https://github.com/mason-org/mason-registry). Hence, installing
packages from this unofficial registry is not supported by Mason maintainers.

## Installation
To source packages from this registry, ensure your setup call to `mason.nvim`
reflects the following table value to the `registries` field:
```lua
require('mason').setup {
  registries = {
    "github:bnwa/mason-registry",
    "github:mason-org/mason-registry",
  }
}
```
It's important that additional registries appear in first in the table as Mason
package lookups resolve with the first registry featuring a matched package name.

Once properly configured, call `:MasonUpdate` to refresh registries registered
with Mason.

## Packages

### Fish Language Server
A third-party [LSP for Fish shell](https://github.com/ndonfris/fish-lsp) maintained by
[ndonfris](https://github.com/ndonfris).

Once installed, you can evoke the LSP server directly:
```lua
vim.lsp.start {
  cmd = { 'fish-language-server', 'start' }
  name = 'fish-language-server',
  root_dir = vim.fs.root(0, { 'config.fish' })
}
```
Or fallback to `nvim-lspconfig` if you have that installed for client configuration instead
of doing so yourself.

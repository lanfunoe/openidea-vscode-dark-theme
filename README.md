# VSCode Theme for OpenIDEA

A dark theme for [OpenIDEA](https://github.com/l0ng-ai/openidea) that follows
the look of Visual Studio Code's default dark theme:

- **Interface:** Dark Modern surfaces, borders, and accent blue.
- **Code:** Dark+ syntax colours. Keywords such as `func`, `var` and `return`
  are blue, function names such as `main` and `Println` are yellow, types are
  teal, variables are light blue, strings are orange, and comments are green.
- **Brackets:** gold, purple and blue bracket-pair colouring, as in VS Code.

## Install

1. Download `lanfunoe.dark-plus-0.1.0.oiplugin` from the
   [latest release](../../releases/latest).
2. In OpenIDEA, open **Settings → Plugins → Install Plugin from Package File**
   and choose the file.
3. Open the plugin's details and apply **VSCode Theme**.

Or install it from the community marketplace: **Settings → Plugins → Available**
and search for "VSCode Theme".

## Known differences from VS Code

- OpenIDEA has a single keyword colour, so control-flow keywords (`if`, `for`,
  `return`, `import`) are the same blue as declaration keywords. In VS Code,
  control-flow keywords are purple.
- Which words get which colour depends on the language plugin's token
  classification. A word that is coloured differently from VS Code usually
  means the language plugin classifies it differently.

## Customising

Colours live in two files:

- `themes/dark-plus.theme.json`: interface tokens (`--bg-app`, `--accent`, …)
- `themes/dark-plus.scheme.json`: editor syntax tokens (`--syn-keyword`,
  `--syn-function`, …)

Edit a value, then rebuild the package (see below).

## Build

Requires the `openidea-plugin` CLI from an OpenIDEA release.

```sh
openidea-plugin check .
openidea-plugin build
openidea-plugin pack . --key lanfunoe.key --publisher lanfunoe
```

The signed package is written to `dist/`. Keep `lanfunoe.key` out of the
repository; it is listed in `.gitignore`.

## Credits

Colours from Visual Studio Code's Dark Modern and Dark+ themes (MIT).
See [NOTICE.md](NOTICE.md). Licensed under the [MIT License](LICENSE).

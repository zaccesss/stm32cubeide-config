# Workflows

| Workflow | Runs on | What it does |
| --- | --- | --- |
| [`settings-lint.yml`](settings-lint.yml) | Push to `main`, every pull request | Checks every `.prefs` fragment line is a `#` note or `key=value` with no key repeated. Checks the key binding XML parses with all 15 bindings. Checks every theme carries the C colours and no Java or newer Terminal keys. Shellchecks `apply.sh` and confirms `mac/apply.sh` and `linux/apply.sh` are identical. Runs `linux/apply.sh` twice on a throwaway workspace to prove every key lands, nothing is backed up and the second run changes nothing, then proves it finds the newest default workspace. Parses `windows/apply.ps1` with PowerShell |
| [`markdownlint.yml`](markdownlint.yml) | Push to `main`, every pull request | Lints every markdown file against [`.markdownlint.json`](../../.markdownlint.json) |

Both are also runnable manually via `workflow_dispatch` from the Actions tab.

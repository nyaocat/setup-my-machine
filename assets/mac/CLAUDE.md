# CLI tool preferences

## Built-in tools first

Before reaching for Bash: search content with **Grep** (ripgrep-backed), find files with **Glob**, read/modify with **Read/Edit/Write**. Shell out only when those cannot express the task.

## In Bash, prefer the modern tool

`rg` over grep · `fd` over find · `sd` over `sed -i` (substitution only) · `choose` over `cut`/`awk '{print $N}'` · `dust`/`duf` over du/df · `procs` over ps · `difft` over diff · `scc` over `wc -l`

By data type: JSON → `jq`, or `gron` when hunting for an unknown key (`gron f.json | rg key`). YAML/TOML/XML → `yq`. CSV/TSV → `mlr`, or `qsv` when large. Code structure (search or rewrite) → `ast-grep` (`sg`). Inside PDF/docx/zip → `rga`. Timing comparisons → `hyperfine`, never `time` by eye.

## Avoid

- Interactive-only: `fzf`, `atuin`, `btm`
- Pagers/decoration: `bat`, `glow` — use `bat --style=plain` or plain `cat` when piping
- `core.pager = delta` is configured, so use **`git --no-pager diff`** in scripts

## Gotchas

- `rg`/`fd` skip .gitignore'd and hidden files by default. Zero hits? Retry with `rg -uu` / `fd -HI` before concluding something does not exist
- `fd` patterns are regex substring matches; pass `-g` for globs
- `sd` backreferences are `$1`, not `\1`
- `eza`/`bat`/`procs` output is human-formatted and unstable — never parse it
- GNU variants available as `ggrep`/`gsed`/`gtar`

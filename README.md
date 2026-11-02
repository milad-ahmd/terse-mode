> [!NOTE]
> **This skill lives in the main collection: [milad-ahmd/agent-skills](https://github.com/milad-ahmd/agent-skills/tree/main/skills/terse-mode)**. Please ⭐ star it there; that's where updates land first.
> Docs: **https://milad-ahmd.github.io/agent-skills/skills/terse-mode/** · Claude Code: `/plugin install all-skills --marketplace milad-ahmd/agent-skills`

<div align="center">

# ✂️ terse-mode

**Shorter, denser agent replies that never cut code, commands, numbers or safety warnings. An Agent Skill for Claude Code, Cline, Cursor, Codex and other AI coding agents.**

[![License: MIT](https://img.shields.io/github/license/milad-ahmd/terse-mode)](LICENSE)
[![Stars](https://img.shields.io/github/stars/milad-ahmd/terse-mode?style=social)](https://github.com/milad-ahmd/terse-mode)
![Category](https://img.shields.io/badge/category-Agent%20Productivity-blue)
![Works with](https://img.shields.io/badge/works%20with-Claude%20Code%20%7C%20Cline%20%7C%20Cursor%20%7C%20Codex-8A2BE2)

[Install](#-install) · [Usage](#-usage) · [How it works](skills/terse-mode/SKILL.md) · [All skills](https://github.com/milad-ahmd/agent-skills)

</div>

> Part of **[agent-skills](https://github.com/milad-ahmd/agent-skills)**, a growing collection of practical skills for AI coding agents.

## 📦 Install

**One command (installs the whole collection):**

```bash
curl -fsSL https://raw.githubusercontent.com/milad-ahmd/agent-skills/main/install.sh | bash -s -- terse-mode
```

**Manually (Claude Code):**

```bash
git clone https://github.com/milad-ahmd/terse-mode /tmp/terse-mode
mkdir -p ~/.claude/skills && cp -r /tmp/terse-mode/skills/terse-mode ~/.claude/skills/
```

**Per project:** copy `skills/terse-mode` into `<project>/.claude/skills/`.
**Any other agent:** paste [`SKILL.md`](skills/terse-mode/SKILL.md) into your rules or system prompt.

## 💬 Usage

Just ask your agent:

```text
terse on
Your answers are too long, skip the preamble and the recap
```

The full workflow, rules and output format are in [`SKILL.md`](skills/terse-mode/SKILL.md).

## 🔎 Sample output

The skill itself is instructions; `terse_check.py` (plain Python 3) measures padding. Real output on a typical padded answer about a failing migration:

```text
$ python3 terse_check.py before.md

line   1  preamble     -2   Great question!
line   1  restate      -11  You're asking why the migration fails on staging but not locally.
line   3  hedge stack  -2   I think, might, possibly
line   3  filler       -4   it's worth noting that
line   3  filler       -1   Basically
line  13  recap        -13  In summary, the migration order is wrong and renaming the file fixes it.
line  13  offer        -14  Let me know if you have any other questions, I'd be happy to help!

101 prose words, about 47 removable (46.5%): offer 14, recap 13, restate 11, filler 5, preamble 2, hedge stack 2
```

`--compare before.md after.md` checks the short version still has every code block, path, number, error line and warning, and exits 1 if anything was lost.

## 🧩 More skills

See the full collection: **[milad-ahmd/agent-skills](https://github.com/milad-ahmd/agent-skills)**.

## 🤝 Contributing

This repo is a read-only mirror. Please open issues and PRs in **[milad-ahmd/agent-skills](https://github.com/milad-ahmd/agent-skills)**.

## 📄 License

[MIT](LICENSE) © Milad Ahmadi

<div align="center">

**If this skill saved you time, a ⭐ helps others find it.**

</div>

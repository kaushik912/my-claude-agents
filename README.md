# my-claude-agents

Canonical library of my tested Claude Code subagents (`.claude/agents/*.md`), pulled
from `agent-testing` once they've proven useful. Flat layout, no per-agent folders —
mirrors Claude Code's own convention, so `.claude/agents/` here is directly usable
as-is (symlink or submodule it into a project) even without any tooling.

## Agents

| Agent | Description |
|---|---|
| [`debugger`](.claude/agents/debugger.md) | Investigates bugs, exceptions, and unexpected behavior — reproduces, isolates root cause, proposes fix. |
| [`jira-triage`](.claude/agents/jira-triage.md) | Pulls a Jira story/bug, summarizes scope, identifies affected code areas. |
| [`code-reviewer`](.claude/agents/code-reviewer.md) | Reviews diffs for bugs, security, style before merge. |
| [`feature-implementer`](.claude/agents/feature-implementer.md) | Implements a feature from Jira acceptance criteria into working code. |
| [`test-runner`](.claude/agents/test-runner.md) | Runs Maven/Gradle test suite and fixes failures. |
| [`doc-writer`](.claude/agents/doc-writer.md) | Documents repo architecture, main modules, and key functionality into README/docs. |

Note: `jira-triage` and `feature-implementer` use `mcp__Atlassian__*` tools — they
need an Atlassian MCP server configured in the target project to work fully.

## Install

Via [`agent-porter`](https://github.com/kaushik912/agent-porter):

```bash
agent-porter install --repo kaushik912/my-claude-agents --agent doc-writer
agent-porter install --repo kaushik912/my-claude-agents --agent doc-writer --dest copilot
agent-porter install --repo kaushik912/my-claude-agents --all
```

Or just copy/symlink `.claude/agents/*.md` straight into your project if you only need Claude format.

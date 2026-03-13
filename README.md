# refactory-template

Template repository for the `refactory-lang` GitHub organization.

## What's Included

- **Speckit** — Specification-driven development framework
  - Extensions: `verify`, `sync`, `review`, `workflows`
  - After-implement hooks: verify → sync → review
- **Claude Code** — `.claude/` commands and skills for speckit workflows
- **Agents** — `.agents/` commands and skills for agent harnesses
- **GitHub Agents** — `.github/agents/` for GitHub Copilot agent definitions
- **VS Code** — `.vscode/settings.json` with speckit prompt recommendations
- **MCP** — `.mcp.json` with codemod CLI server
- **CLAUDE.md / AGENTS.md** — Codemod skill discovery

## Usage

Each repo in the refactory-lang org should be initialized from this template:

```bash
# Copy template contents into a new repo
cp -R refactory-template/.specify <repo>/.specify
cp -R refactory-template/.claude <repo>/.claude
cp -R refactory-template/.agents <repo>/.agents
cp -R refactory-template/.github/agents <repo>/.github/agents
cp -R refactory-template/.vscode <repo>/.vscode
cp refactory-template/.mcp.json <repo>/.mcp.json
cp refactory-template/.gitignore <repo>/.gitignore
cp refactory-template/CLAUDE.md <repo>/CLAUDE.md
cp refactory-template/AGENTS.md <repo>/AGENTS.md
```

Then customize CLAUDE.md, AGENTS.md, and .gitignore for the specific repo.

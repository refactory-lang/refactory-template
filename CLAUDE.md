<!-- codemod-skill-discovery:begin -->
## Codemod Skill Discovery
This section is managed by `codemod` CLI.

- Core skill: `.agents/skills/codemod/SKILL.md`
- Package skills: `.agents/skills/<package-skill>/SKILL.md`
- List installed Codemod skills: `npx codemod agent list --harness antigravity --format json`

<!-- codemod-skill-discovery:end -->

## Project: refactory-template

Common configuration template for all repositories in the [refactory-lang](https://github.com/refactory-lang) organization. Each repo is initialized from this template and customized for its specific needs.

### Architecture

- **Speckit** (`.specify/`): Specification-driven development framework with extensions (verify, sync, review, workflows) and after-implement hooks
- **Claude Code** (`.claude/`): Commands and skills for speckit workflows
- **Agents** (`.agents/`): Commands and skills for agent harnesses
- **GitHub Agents** (`.github/agents/`): GitHub Copilot agent definitions
- **VS Code** (`.vscode/`): Settings with speckit prompt recommendations
- **MCP** (`.mcp.json`): Codemod CLI server configuration
- **CLAUDE.md / AGENTS.md**: Codemod skill discovery (AGENTS.md is a symlink to CLAUDE.md)

### Usage

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

Then customize CLAUDE.md and .gitignore for the specific repo.

### Conventions

- AGENTS.md is always a symlink to CLAUDE.md -- only edit CLAUDE.md
- Each repo should have its own project-specific sections added to CLAUDE.md after the codemod skill discovery block


### Speckit Workflow

This repo uses [speckit](https://github.com/speckit) for specification-driven development.

- **Specs**: `specs/<NNN-feature-name>/spec.md` — feature specifications
- **Plans**: `specs/<NNN-feature-name>/plan.md` — implementation plans with tasks
- **Checklists**: `specs/<NNN-feature-name>/checklists/` — quality gates
- **Templates**: `.specify/templates/` — spec, plan, task, checklist templates
- **Extensions**: `.specify/extensions/` — verify, sync, review, workflow hooks

**Branch convention**: Feature branches are named `<NNN>-<short-name>` matching the spec directory (e.g., `001-milestone1-pipeline`).

**Issue → Spec flow**: Issues labeled `spec-ready` trigger the `spec-ready-notify` workflow, which assigns Copilot to run the speckit workflow and produce a spec + plan + tasks.

# Skill

## What is a skill

a skill is a foldere containing:

- SKILL.md (required): Instructions in Markdown with YAML frontmatter
- scripts/ (optional): Executable code(Python, Bash, etc.)
- references/ (optional): Documentation loaded as needed
- assets/ (optional): Templates, fronts, icons used in output

## Progressive Disclusure

skills uses a three-level system:

- First level (YAML frontmatter): Always loaded in Claude's system prompt. Provides just enought information for Claude to know when each skill should be used without loading all of it into context.
- Second level (SKILL.md): Loaded when claude thinks the skill is relevent to the current task. Contains full instructions and guidance
- Third Level (Linked files): Additional files bundled within the skill directory that Claude can choose to navigate and discover only as needed.

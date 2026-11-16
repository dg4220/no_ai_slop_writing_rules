---
name: readme-writer
description: Write, revise, and review accurate, useful README files for repositories in the bu-ist GitHub organization. Use when documenting a repository, development setup, commands, configuration, or project operations.
---

# README Writer

Write README files that help the intended reader understand a repository and complete their next task. Prefer accurate, tested instructions over polished but unsupported claims.

## First: inspect the repository

Before drafting or changing a README:

1. Identify the repository’s purpose and likely readers from its code, existing documentation, and metadata.
2. Inspect relevant files, as available:
   - Existing README files and documentation
   - `composer.json`, lock files, and PHP configuration
   - `package.json` and other build manifests
   - `Dockerfile`, Compose files, and container configuration
   - `Makefile`, task-runner files, and scripts
   - `.env.example` or equivalent example configuration
   - CI workflows and tests
3. Confirm that commands, filenames, ports, defaults, and paths in the README match the repository.
4. Follow established conventions in the repository. Do not infer a `bu-ist` organization-wide style from the organization name alone.

If information cannot be verified, omit it or mark it clearly as something the maintainers must supply. Never invent setup steps, supported versions, deployment procedures, contacts, badges, or guarantees.

## Source of truth

Use sources in this order:

1. The repository’s actual code and configuration
2. Documentation already maintained with the repository
3. Relevant `bu-ist` organization guidance, if present and applicable
4. Upstream tool documentation for general behavior

Upstream examples can guide the structure and level of detail, but do not copy their project-specific instructions into a `bu-ist` README. In particular, confirm that upstream defaults apply to this repository before documenting them.

## Writing principles

- Use plain, direct language. Address the reader as “you” when it makes instructions clearer.
- Start with a short explanation of what the project does and who it is for.
- Prefer actionable headings and concise paragraphs.
- Put the shortest reliable path to a useful result near the top.
- Use numbered steps for procedures and fenced code blocks for commands.
- Explain where a command should be run if that is not obvious.
- Use the project’s existing terminology; define specialized terms when needed.
- Avoid marketing language, filler, repeated explanations, and generic claims such as “easy to use.”
- Do not preserve a particular brand or individual’s voice unless the repository explicitly requires it.
- Do not duplicate detailed documentation unnecessarily. Link to maintained docs using working, repository-relative links where possible.

## Recommended README structure

Use only the sections that help a reader of this repository. A typical README may include:

1. **Project name and summary**
2. **Status or intended audience**, only when known and useful
3. **Prerequisites**
4. **Quick start**
5. **Configuration**
6. **Development workflow**
7. **Tests and checks**
8. **Architecture or project layout**, if it helps contributors
9. **Deployment or operations**, only when documented and appropriate
10. **Troubleshooting**
11. **Contributing, support, and license**, only when authoritative information exists

Do not add empty sections to make the README look complete.

## Setup and command accuracy

- Copy commands from project scripts, CI configuration, or other verified sources.
- Check that commands work from the directory named in the instructions.
- State prerequisites and version constraints only when they are supported by project files or maintained documentation.
- Distinguish local development commands from production or deployment commands.
- Do not claim to have run a command or test unless you actually did.
- When validation is not possible, say what should be checked rather than presenting an unverified command as confirmed.
- Avoid commands that delete data or alter shared environments unless they are necessary, clearly explained, and safely scoped.

## WordPress and PHP repositories

When relevant to the project, document:

- The verified PHP, WordPress, Composer, and database requirements
- How dependencies are installed and how the application is started locally
- Whether the project is a plugin, theme, WordPress application, or development tool
- Where project code and configuration belong
- How to run the project’s actual test, lint, or formatting commands
- Any setup steps specific to this repository, such as required local configuration

Do not assume all WordPress projects use the same directory layout, dependency manager, local environment, or database configuration. Do not instruct readers to edit generated or vendor-managed files unless the project’s workflow requires it.

## Docker and containerized development

When relevant, document the setup that the repository actually uses:

- Required container tools and verified versions, if specified
- The Compose or container command used to start and stop the environment
- Which services are started and how the reader accesses the application
- Configuration variables and the location of any example environment file
- Which data is persisted and how to reset it, if that behavior is known
- How to view logs or run tests inside the relevant container, if supported

Never publish secrets. Do not present example credentials as safe for shared, staging, or production environments. Explain destructive volume-reset commands before showing them, and only include them when verified and necessary.

## Configuration and security

- Document only configuration variables that the application actually reads.
- For each variable, give its purpose and a verified default or mark the default as unspecified.
- Make clear when a value is an example or must be supplied by the user.
- Do not include real credentials, tokens, personal data, or internal URLs unless explicitly approved for publication.
- Do not imply that a development configuration is suitable for production.

## Links and maintenance

- Prefer links to files and docs in the same repository when they are relevant.
- Check relative link paths against the repository layout.
- Link to upstream documentation for general tool behavior; keep project-specific instructions in the project README.
- Avoid links to transient branches or undocumented internal resources when a stable link is available.
- Do not add badges unless their target and status are known and the project already uses or requests them.

## Final review

Before presenting a README change, check:

- Does the opening explain the project without unsupported claims?
- Can the intended reader find a verified starting point quickly?
- Do commands, paths, filenames, links, and configuration names match the repository?
- Are optional sections clearly distinguished from required steps?
- Are security-sensitive details absent?
- Is any content duplicated, speculative, or left over from another project?
- Did you report validation honestly?

When proposing edits, summarize what changed and call out any information maintainers still need to verify.

# New PR Command (npr)

## Purpose
Create a new Graphite branch with a conventional commit message following our task-driven workflow.

**When user types `/npr`, immediately execute the `gt create` bash command without explanation or preamble. User can preview/approve at the bash command stage.**

## Usage

### Basic Format
```bash
gt create -m "type(scope): description"
```

### Recommended Usage
```bash
gt create -m "type(scope): description" --all
```


## Conventional Commit Types
- `feat`: New feature
- `fix`: Bug fix  
- `docs`: Documentation changes
- `refactor`: Code refactoring
- `test`: Adding/updating tests
- `chore`: Maintenance tasks
- `perf`: Performance improvements
- `style`: Code style changes (formatting, etc.)

## Common Scopes for Brewww

### Client-Specific Scopes
- `cw`: Christine Wessa site
- `jh`: Joseph House site  
- `mb`: Mary Bielski site
- `kw`: Kevin Wessa site
- `ho`: His Own site
- `bs`: Brewww Studio site

### Feature/Package Scopes
- `tasks`: Task management system
- `seo`: SEO functionality
- `forms`: Form components/validation
- `ui`: UI components
- `payload`: Payload CMS related
- `utils`: Utility functions
- `validation`: Form validation
- `data-options`: Shared data structures
- `config`: Configuration changes
- `deps`: Dependencies

### Multi-scope Pattern
Use comma separation for changes affecting multiple areas:
- `cw,forms`: Client-specific form changes
- `ui,payload`: UI components for Payload
- `utils,validation`: Utility functions for validation

## Examples

### Client-Specific Work
```bash
gt create -m "feat(cw): add custom contact form for Christine Wessa" --all
gt create -m "fix(jh): resolve menu navigation issue on Joseph House site" --all
gt create -m "refactor(mb): optimize image gallery for Mary Bielski" --all
```

### Shared Package Work
```bash
gt create -m "feat(seo): implement google preview card with image support" --all
gt create -m "fix(validation): resolve email validation edge cases" --all
gt create -m "refactor(forms): extract common form utilities" --all
```

### Cross-Client Features
```bash
gt create -m "feat(cw,forms): integrate payload-forms with Christine Wessa site" --all
gt create -m "fix(ui,payload): resolve form field rendering across all sites" --all
gt create -m "refactor(seo,cw,jh): standardize meta tag generation" --all
```

### Documentation & Maintenance
```bash
gt create -m "docs(tasks): add images-infrastructure, slug-uniqueness, and cloudflare-loader-security docs" --all
gt create -m "chore(deps): update payload cms to latest version" --all
gt create -m "test(utils): add comprehensive url utility tests" --all
```

## Workflow Integration

1. **Start from task**: Reference task file when creating commit
2. **Atomic commits**: Each commit should represent one logical change
3. **Stack related changes**: Use Graphite's stacking for related features
4. **Submit stack**: Use `gt submit --stack` when ready for review

## Task-to-PR Mapping

When implementing tasks, create PRs that map to task completion:

```bash
# From TASK.SLUG-UNIQUENESS-INVESTIGATION.md
gt create -m "feat(payload): implement multi-tenant slug uniqueness validation" --all

# From TASK.CLOUDFLARE-LOADER-SECURITY.md  
gt create -m "fix(ui): add focal point validation for cloudflare image loader" --all

# From TASK.URL-ENVIRONMENT-CONSOLIDATION.md
gt create -m "refactor(config): consolidate URL environment variables" --all
```

## Quick Reference

```bash
# Create new branch/commit
gt create -m "type(scope): description" --all

# View current stack
gt log

# Submit current stack
gt submit --stack

# Rebase stack on latest main
gt sync

# Navigate stack
gt up    # Move up in stack
gt down  # Move down in stack
```

## Benefits for Our Workflow

1. **Atomic commits**: Each task becomes a focused commit
2. **Stacked PRs**: Related tasks can build on each other
3. **Clean history**: Conventional commits create readable history
4. **Easy review**: Small, focused PRs are easier to review
5. **Task traceability**: Commit messages reference task scope
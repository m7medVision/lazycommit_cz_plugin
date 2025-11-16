# cz-lazycommit

A Commitizen plugin that integrates with lazycommit CLI tool to generate AI-powered commit messages.

## What it does

1. Stages your git changes
2. Calls lazycommit to generate AI-powered commit message suggestions
3. Shows you the generated commit messages
4. Allows you to confirm or edit the message
5. Creates the commit with the final message

## Installation

Install the plugin:
```bash
pip install cz-lazycommit
# or if you using Arch Linux
 uv tool install commitizen --with cz-lazycommit
```

Install lazycommit:
```bash
go install github.com/m7medvision/lazycommit@latest
lazycommit config set  # Interactive setup
```

## Usage

Stage your changes and commit:
```bash
git add <files>
cz --name cz_lazycommit commit
```


### With Lazygit

```yaml
customCommands:
  - key: "C"
    command: "git cz --name cz_lazycommit commit"
    description: "commit with commitizen"
    context: "files"
    loadingText: "opening commitizen commit tool"
    subprocess: true
```


The plugin will:
- Generate AI-powered commit suggestions using lazycommit
- Let you select and edit messages
- Handle conventional commit format automatically
- Support version bump detection (major/minor/patch)

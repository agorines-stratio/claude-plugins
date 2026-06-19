# claude-plugins

Personal Claude Code plugins for agorines-stratio.

## Plugins

### github-search

Search code in GitHub repositories using the GitHub MCP.

**Requirements:** `GITHUB_PERSONAL_ACCESS_TOKEN` env var with read access to target repos.

**Usage:**
```
/github-search skip_keos_yaml_check repo:Stratio/keos-installer
/github-search helm_chart_upgrade org:Stratio lang:yaml
```

## Installation

```
/plugin add-marketplace agorines-personal https://github.com/agorines-stratio/claude-plugins
/plugin install github-search@agorines-personal
```

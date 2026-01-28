# Vincent's Personal Claude Code Plugins

Personal plugin marketplace for Claude Code plugins.

## Marketplace Information

- **Name**: vincent-personal-plugins
- **Owner**: Vincent

## Available Plugins

### example-plugin v0.1.0

A simple example plugin to test and validate Claude Code plugin marketplace functionality.

**Components**:
- Commands: `/example-hello`, `/example-info`
- Agent: example-validator
- Skill: example-greeting
- Hook: SessionStart

**Purpose**: Validates marketplace discovery, loading, and execution mechanisms.

## Installation

### Add Marketplace

Add this marketplace to your Claude Code configuration:

```bash
claude marketplace add vincent-personal-plugins /path/to/claude-code-plugins
```

Or if you've pushed to GitHub:

```bash
claude marketplace add vincent-personal-plugins github:username/claude-code-plugins
```

### Install Plugin from Marketplace

```bash
claude plugin install example-plugin --marketplace vincent-personal-plugins
```

### Or Install Plugin Directly

```bash
claude plugin install ./example-plugin
```

## Testing the Marketplace

After adding the marketplace, verify it works:

1. **List marketplace plugins**:
   ```bash
   claude marketplace plugins vincent-personal-plugins
   ```

2. **Install the example plugin**:
   ```bash
   claude plugin install example-plugin
   ```

3. **Test plugin components**:
   ```bash
   # Test command
   /example-hello

   # Test info command
   /example-info
   ```

4. **Test agent**: Ask Claude to "validate my code"

5. **Test skill**: Mention "example plugin" in conversation

6. **Test hook**: Start a new session and look for welcome message

## Repository Structure

```
claude-code-plugins/
├── .claude-plugin/
│   └── marketplace.json    # Marketplace definition
├── example-plugin/         # Example plugin
│   ├── .claude-plugin/
│   │   └── plugin.json
│   ├── commands/
│   ├── agents/
│   ├── skills/
│   └── hooks/
└── README.md              # This file
```

## Adding More Plugins

To add new plugins to this marketplace:

1. Create plugin directory: `mkdir -p new-plugin/.claude-plugin`
2. Create plugin.json manifest
3. Add plugin components (commands, agents, skills, hooks)
4. Update `.claude-plugin/marketplace.json`:
   ```json
   {
     "plugins": [
       ...,
       {
         "name": "new-plugin",
         "source": "./new-plugin",
         "description": "Plugin description",
         "version": "1.0.0"
       }
     ]
   }
   ```

## Resources

- [Claude Code Plugin Documentation](https://code.claude.com/docs/en/plugins)
- [Plugin Marketplace Guide](https://code.claude.com/docs/en/plugin-marketplaces)
- [Official Plugins Repository](https://github.com/anthropics/claude-plugins-official)

## License

MIT

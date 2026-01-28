# Testing Guide for Example Plugin

This guide helps you verify that the example-plugin and marketplace are working correctly.

## Prerequisites

- Claude Code CLI installed
- This repository cloned locally

## Testing Steps

### 1. Add the Marketplace

From the repository root directory:

```bash
# Add marketplace using absolute path
claude marketplace add vincent-personal-plugins /Users/vincent/projects/claude-code-plugins

# Or use relative path from your location
claude marketplace add vincent-personal-plugins $(pwd)
```

**Expected output**: Marketplace added successfully

### 2. Verify Marketplace Registration

```bash
# List all marketplaces
claude marketplace list
```

**Expected output**: Should see `vincent-personal-plugins` in the list

### 3. List Marketplace Plugins

```bash
# List plugins in this marketplace
claude marketplace plugins vincent-personal-plugins
```

**Expected output**: Should see `example-plugin v0.1.0`

### 4. Install the Plugin

```bash
# Install from marketplace
claude plugin install example-plugin --marketplace vincent-personal-plugins

# Or install directly from directory
claude plugin install ./example-plugin
```

**Expected output**: Plugin installed successfully

### 5. Verify Plugin Installation

```bash
# List installed plugins
claude plugin list
```

**Expected output**: Should see `example-plugin` with status `enabled`

### 6. Test Session Start Hook

Start a new Claude Code session:

```bash
cc
```

**Expected output**: At session start, you should see:
```
🎉 Example plugin loaded successfully!
```

### 7. Test Commands

Within the Claude Code session:

#### Test Hello Command

```
/example-hello
```

**Expected output**:
```
👋 Hello from example-plugin!

This command verifies that slash commands are working correctly.
```

#### Test Info Command

```
/example-info
```

**Expected output**: Should display plugin metadata (name, version, author, etc.)

### 8. Test Agent

Ask Claude to validate code:

```
Can you validate the code in example-plugin/commands/example-hello.md?
```

**Expected behavior**: The `example-validator` agent should activate and perform basic validation checks.

### 9. Test Skill

Mention the plugin in conversation:

```
Tell me about the example plugin components.
```

**Expected behavior**: The `example-greeting` skill should activate, providing information about the plugin.

## Verification Checklist

- [ ] Marketplace added successfully
- [ ] Marketplace appears in list
- [ ] Plugin appears in marketplace plugins
- [ ] Plugin installs without errors
- [ ] Plugin appears in installed plugins list
- [ ] SessionStart hook prints welcome message
- [ ] `/example-hello` command works
- [ ] `/example-info` command works
- [ ] example-validator agent activates on request
- [ ] example-greeting skill activates when discussing plugin

## Troubleshooting

### Marketplace not found

**Issue**: `claude marketplace list` doesn't show the marketplace

**Solution**:
```bash
# Remove and re-add with absolute path
claude marketplace remove vincent-personal-plugins
claude marketplace add vincent-personal-plugins /absolute/path/to/claude-code-plugins
```

### Plugin not installing

**Issue**: `Plugin not found in marketplace`

**Solution**: Verify `.claude-plugin/marketplace.json` exists and is valid JSON

### Commands not appearing

**Issue**: Commands don't show in `/help`

**Solution**:
```bash
# Restart Claude Code session
exit
cc
```

### Hook not firing

**Issue**: No welcome message on session start

**Solution**: Check that `hooks/hooks.json` exists and is valid JSON

### Agent not triggering

**Issue**: Agent doesn't activate

**Solution**: Try explicit invocation or use more specific trigger phrases

## Development Testing

For rapid development testing without marketplace:

```bash
# Test plugin directly from directory
cc --plugin-dir ./example-plugin

# Or symlink to Claude plugins directory
ln -s $(pwd)/example-plugin ~/.claude/plugins/example-plugin
```

## Success Criteria

✅ All components load without errors
✅ All commands execute successfully
✅ Agent can be triggered
✅ Skill activates on context
✅ Hook fires on session start
✅ Marketplace discovery works correctly

## Next Steps

After verifying the example plugin works:

1. Use this as a template for creating new plugins
2. Add more plugins to the marketplace
3. Share the marketplace URL with others
4. Iterate on plugin functionality

## Resources

- [Claude Code Plugin Documentation](https://code.claude.com/docs/en/plugins)
- [Plugin Development Guide](https://code.claude.com/docs/en/plugin-development)
- Example Plugin Source: `./example-plugin/`

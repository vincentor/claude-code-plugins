# Example Plugin

A simple example plugin to test and validate Claude Code plugin marketplace functionality.

## Overview

This plugin demonstrates all core plugin components:
- **Commands**: User-invoked slash commands
- **Agents**: Autonomous task execution
- **Skills**: Auto-activating knowledge modules
- **Hooks**: Event-driven automation

## Installation

### From Marketplace

```bash
claude plugin install example-plugin
```

### From Local Directory

```bash
claude plugin install ./example-plugin
```

## Components

### Commands

- `/example-hello` - Simple greeting command
- `/example-info` - Display plugin information

### Agents

- `example-validator` - Basic code style validation agent

### Skills

- `example-greeting` - Activates when discussing plugins or greetings

### Hooks

- `SessionStart` - Prints welcome message when session starts

## Usage Examples

### Using Commands

```bash
# Simple greeting
/example-hello

# Show plugin info
/example-info
```

### Triggering Agent

Ask Claude to validate code style, and the example-validator agent may assist.

### Activating Skills

Mention "example plugin" or discuss plugin-related topics to activate the greeting skill.

## Purpose

This plugin serves as:
1. **Marketplace validation** - Tests plugin discovery and loading
2. **Reference template** - Example structure for new plugins
3. **Component showcase** - Demonstrates all plugin component types

## License

MIT

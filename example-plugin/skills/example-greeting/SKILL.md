---
name: Example Greeting Skill
description: This skill activates when users discuss the example plugin, demonstrating how skills auto-activate based on context. Use when users mention "example plugin", ask about plugin functionality, or discuss plugin components.
version: 0.1.0
---

# Example Greeting Skill

This skill demonstrates how Claude Code skills automatically activate based on user context.

## Purpose

Provide friendly, informative guidance when users interact with the example plugin or discuss plugin-related topics.

## When This Activates

You'll recognize activation is appropriate when the user:
- Mentions "example plugin" explicitly
- Asks about plugin components (commands, agents, skills, hooks)
- Discusses how the marketplace works
- Questions plugin functionality
- Refers to testing or validation of plugins

## What To Do

When this skill activates:

1. **Acknowledge the context** - Show you understand they're working with the example plugin
2. **Provide relevant guidance** - Offer helpful information about the specific component or concept
3. **Point to resources** - Reference the README or specific files when appropriate
4. **Keep it friendly** - Use a welcoming, educational tone

## Core Knowledge

### Plugin Components

The example plugin includes:

- **Commands**: `/example-hello` (simple greeting), `/example-info` (displays plugin metadata)
- **Agent**: `example-validator` (basic code style validation)
- **Skill**: This skill you're using now (context-aware activation)
- **Hook**: SessionStart hook (prints welcome message)

### Plugin Purpose

This plugin serves three goals:
1. Validate marketplace functionality (discovery, loading, execution)
2. Provide a reference template for creating new plugins
3. Demonstrate all core plugin component types

### Testing Verification

To verify the plugin works:
- Commands should appear in `/help` and execute correctly
- Agent should trigger when validating code
- Skills should activate on relevant context (like now!)
- Hook should print message when sessions start

## Response Style

- **Concise**: Keep explanations brief but complete
- **Practical**: Focus on actionable information
- **Educational**: Help users understand plugin mechanics
- **Encouraging**: Celebrate when things work correctly

## Example Interactions

**User**: "Tell me about the example plugin"
**You**: "👋 The example plugin is a demonstration plugin that showcases all core Claude Code plugin components. It includes two commands (/example-hello and /example-info), a validation agent, this greeting skill, and a session start hook. It's designed to test marketplace functionality and serve as a reference for creating new plugins."

**User**: "How do I test if the plugin is working?"
**You**: "Great question! Here's how to verify each component:
1. Run `/example-hello` to test commands
2. Ask me to validate code to trigger the agent
3. Mention the plugin (like now!) to activate this skill
4. Check console output when starting a session for the hook message"

## Important Notes

- This is a **demonstration skill** - it's intentionally simple
- Real-world skills would have deeper domain knowledge
- The goal is to show auto-activation mechanics
- Skills should be triggered by context, not explicit commands

Keep your assistance focused, practical, and welcoming!

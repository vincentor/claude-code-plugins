---
name: example-info
description: Display information about the example plugin
argument-hint: ""
allowed-tools: ["Read"]
---

# Example Info Command

Display metadata and information about the example plugin.

## Instructions

When this command is invoked:

1. Read the plugin manifest file at `example-plugin/.claude-plugin/plugin.json`
2. Extract and display the following information:
   - Plugin name
   - Version
   - Description
   - Author name
   - Keywords
3. Format the output in a clean, readable way
4. If the file cannot be read, show a friendly error message

## Example Output

```
📦 Example Plugin Information

Name: example-plugin
Version: 0.1.0
Description: A simple example plugin to test plugin marketplace functionality
Author: Vincent
Keywords: example, demo, marketplace-test

This plugin demonstrates all core plugin component types.
```

## Notes

- Uses Read tool to access the plugin.json file
- Demonstrates file I/O in commands
- Provides useful debugging information

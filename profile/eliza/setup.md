# Eliza Integration Guide

This guide walks you through setting up an Eliza agent with the Grix plugin.

## Getting Started

### Setup Requirements

1. Node.js Setup:
   - Install and use Node version 23 using nvm

   ```bash
   nvm install 23
   nvm use 23
   ```

2. Clone Eliza Repository:

   ```bash
   git clone https://github.com/elizaOS/eliza
   cd eliza
   git checkout $(git describe --tags `git rev-list --tags --max-count=1`)
   ```

3. Install Dependencies:

   ```bash
   pnpm install --no-frozen-lockfile
   ```

## Environment Configuration

Create a `.env` file in the main Eliza directory with your API keys:

```env
GRIX_API_KEY=***
OPENAI_API_KEY=***
```

## Plugin Installation

1. List available plugins:

   ```bash
   npx elizaos plugins list
   ```

2. Install Grix plugin:

   ```bash
   npx elizaos plugins add @elizaos-plugins/plugin-grix
   ```

## Launch Instructions

1. Build the project:

   ```bash
   pnpm run build
   ```

2. Start Eliza:

   ```bash
   sh scripts/start.sh
   ```

3. Access the interface at: <http://localhost:5173/>

## Character Configuration

1. Create a character file at `/characters/[name].character.json`
2. Configure the following in your character file:
   - Personality traits
   - Behavior patterns
   - Agent capabilities
   - Model providers and clients
   - Plugins (example: `"plugins": ["@elizaos-plugins/plugin-grix"]`)

## Example Character Configuration

We provide an example character configuration in [hermione.character.json](hermione.character.json). This character is designed to work well with the Grix plugin and demonstrates best practices for character configuration.

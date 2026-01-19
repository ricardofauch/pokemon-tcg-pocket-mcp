markdown# Pokemon TCG Pocket MCP Server

A Model Context Protocol (MCP) server that provides access to Pokemon Trading Card Game Pocket data through the TCGdex API. This server enables Claude and other MCP clients to search and retrieve detailed information about TCG Pocket cards, sets, and boosters.

## Features

- 🔍 **Card Search** - Search for cards by name, type, HP, rarity, and more
- 📦 **Set Information** - Get all available TCG Pocket sets and their cards
- 🎴 **Card Details** - Retrieve comprehensive information about specific cards
- 🌍 **Multilingual Support** - Available in 9 languages (EN, FR, DE, ES, IT, PT, JA, KO, ZH-CN)
- 🎁 **Booster Tracking** - Find which booster packs contain specific cards
- ⭐ **Rarity Filtering** - Filter by TCG Pocket rarity system (diamonds, stars, crown)

## Prerequisites

- Node.js 18 or higher
- npm or yarn
- Claude Desktop App or any MCP-compatible client

## Installation

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/pokemon-tcgp-mcp-server.git
cd pokemon-tcgp-mcp-server
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Build the Project
```bash
npm run build
```

## Configuration

### For Claude Desktop

Add the server to your Claude Desktop configuration file:

**MacOS**: `~/Library/Application Support/Claude/claude_desktop_config.json`

**Windows**: `%APPDATA%\Claude\claude_desktop_config.json`
```json
{
  "mcpServers": {
    "pokemon-tcgp": {
      "command": "node",
      "args": [
        "/absolute/path/to/pokemon-tcgp-mcp-server/dist/index.js"
      ]
    }
  }
}
```

**Important**: Replace `/absolute/path/to/pokemon-tcgp-mcp-server` with the actual absolute path to your cloned repository.

### For Other MCP Clients

Refer to your MCP client's documentation for how to add custom servers. You'll need to point to the built `dist/index.js` file.

## Usage Examples

### Search for Cards
```
Search for all Pikachu cards in TCG Pocket
```
```
Find all cards with 100 HP
```
```
Show me all Fire type cards from the Genetic Apex set
```
```
Which cards are available in the Mewtwo booster pack?
```

### Get Set Information
```
What TCG Pocket sets are available?
```
```
Show me all cards from set A1
```

### Get Card Details
```
Get details for card A1-001
```
```
What are the attacks on Charizard ex?
```

## Available Tools

### tcgp-card-search

Search for Pokemon TCG Pocket cards with various filters.

**Parameters:**
- `name` (optional): Card name to search for
- `setId` (optional): Set ID (e.g., "A1", "A1a")
- `types` (optional): Pokemon types (e.g., ["Fire", "Water"])
- `hp` (optional): HP value
- `stage` (optional): Evolution stage ("Basic", "Stage1", "Stage2")
- `rarity` (optional): Card rarity ("◇", "◇◇", "◇◇◇", "◇◇◇◇", "☆", "☆☆", "☆☆☆", "♛")
- `category` (optional): Card category ("Pokemon", "Trainer", "Energy")
- `suffix` (optional): Special suffix (e.g., "EX")
- `booster` (optional): Booster pack name (e.g., "Mewtwo", "Charizard", "Pikachu")
- `language` (optional): Language code (default: "en")

### tcgp-get-sets

Get all available TCG Pocket sets.

**Parameters:**
- `language` (optional): Language code (default: "en")

### tcgp-get-set-cards

Get all cards from a specific set.

**Parameters:**
- `setId`: The set ID (e.g., "A1", "A1a")
- `language` (optional): Language code (default: "en")

### tcgp-get-card

Get detailed information about a specific card.

**Parameters:**
- `cardId`: The card ID (e.g., "A1-001", "A1a-019")
- `language` (optional): Language code (default: "en")

## TCG Pocket Sets

Current available sets:
- **A1** - Genetic Apex
- **A1a** - Mythical Island

## Supported Languages

- `en` - English
- `fr` - French
- `de` - German
- `es` - Spanish
- `it` - Italian
- `pt` - Portuguese
- `ja` - Japanese
- `ko` - Korean
- `zh-CN` - Chinese (Simplified)

## Development

### Project Structure
```
pokemon-tcgp-mcp-server/
├── src/
│   └── index.ts          # Main server implementation
├── dist/                 # Compiled JavaScript (generated)
├── package.json
├── tsconfig.json
└── README.md
```

### Build
```bash
npm run build
```

### Watch Mode (for development)
```bash
npm run watch
```

## Troubleshooting

### Server Not Appearing in Claude Desktop

1. Verify the path in `claude_desktop_config.json` is absolute and correct
2. Ensure the project is built (`npm run build`)
3. Restart Claude Desktop completely
4. Check Claude Desktop logs for errors

### API Errors

If you encounter API errors:
- Check your internet connection
- Verify the TCGdex API is accessible: https://api.tcgdex.net/v2/en/series/tcgp
- Ensure you're using valid set IDs and card IDs

## Data Source

This server uses the [TCGdex API](https://www.tcgdex.net/) which provides comprehensive Pokemon TCG data including TCG Pocket cards.

## License

MIT

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Credits

- Pokemon TCG Pocket data provided by [TCGdex](https://www.tcgdex.net/)
- Built with the [Model Context Protocol SDK](https://github.com/modelcontextprotocol)

## Disclaimer

This is an unofficial fan-made tool. Pokemon and Pokemon TCG are trademarks of Nintendo, Cre

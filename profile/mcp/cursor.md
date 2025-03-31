# 🔌 How to Connect GRIX MCP to Cursor

This guide walks you through connecting the GRIX MCP (Model Control Protocol) to the Cursor editor. You’ll generate your GRIX API key, configure it in Cursor, and verify it’s working.

---

## ✅ Step 1: Generate Your GRIX API Key

1. Go to the **GRIX app**.
2. Navigate to: Devs → API
3. Click **"Generate API Key"**.
4. Ensure you have **credits** available in your GRIX account (they're required for MCP usage).

---

## ⚙️ Step 2: Add GRIX MCP in Cursor

1. Open **Cursor**.
2. Go to:Settings → MCP
3. Click **"Add new Global MCP server"**.

Now, depending on whether you already have MCPs set up or not, do the following:

---

### 📦 If You Don’t Have Any Existing MCPs

Paste the entire structure below into the configuration field:

```json
{
"mcpServers": {
 "GRIX_mcp": {
   "command": "npx",
   "args": ["-y", "@grixprotocol/grix_mcp"],
   "env": {
     "GRIX_API_KEY": "your_key"
   }
 }
}
}
```
🔐 Replace "your_key" with your actual API key from Step 1.

### 🧩 If You Already Have Other MCPs Configured
Just add the following inside your existing mcpServers object:
```json
"GRIX_mcp": {
  "command": "npx",
  "args": ["-y", "@grixprotocol/grix_mcp"],
  "env": {
    "GRIX_API_KEY": "your_key"
  }
}
```
Replace "your_key" with your actual GRIX API key.
Make sure your JSON stays valid (add commas where needed).

### ✅ Step 3: Verify Connection
1. Head back to: Cursor → Settings → MCP
2. If you’ve added credits to your GRIX account, you’ll see a 🟢 green dot next to GRIX_mcp.
This means your connection is live and ready to use.

### 🧠 Troubleshooting

#### ❌ No green dot?

  * Check your API key.

- Make sure you have credits on GRIX.

* Try restarting Cursor.

#### 🛠 Still stuck?

Reach out to the GRIX community or support team for help.

### Happy building with GRIX + Cursor! 💻✨


Let me know if you'd like this turned into a downloadable `.md` or `.pdf` file, or styled differently (e.g., Notion, GitHub, Obsidian).


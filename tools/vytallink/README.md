# [VytalLink](https://vytallink.xmartlabs.com/)

## What is it

VytalLink is a mobile app that connects your wearable devices and health apps (Apple Health, Google Fit) to AI assistants like ChatGPT and Claude. It lets you query your own health data using natural language — **no coding required** to get started, but fully extensible for developers via MCP, REST API, and WebSocket.

## How it works

![VytalLink high-level architecture](https://blog.xmartlabs.com/images/frame-2.png)

## What problem does it solve

Getting health data out of wearables and into a usable format is painful. Each device has its own app, its own export format, and its own limitations. VytalLink acts as a bridge: it reads from your health sources and exposes that data to AI assistants so you can ask things like *"How was my sleep this week?"* or *"Show me my heart rate trends during workouts"* — without writing a single API call or data pipeline.

For hackathon participants, this means **instant access to real health data** without needing to reverse-engineer wearable APIs or build data ingestion pipelines from scratch.

## Quickstart

### Option A: No-code (ChatGPT)

1. Install the VytalLink app ([iOS](https://apps.apple.com/uy/app/vytallink/id6752308627) / [Android](https://play.google.com/))
2. Connect your health data source (Apple Health or Google Fit)
3. Tap **"Get Word + PIN"** in the app to generate your credentials (e.g. `HEALTH7` + `sunset42`)
4. Open ChatGPT and search for the **"vytalLink"** GPT
5. Paste your credentials when prompted
6. Start asking questions about your health data

### Option B: Claude Desktop (Bundle)

1. Install the VytalLink app and connect your health source
2. Download the Claude Desktop bundle from [vytallink.xmartlabs.com](https://vytallink.xmartlabs.com)
3. Double-click to install — no CLI needed
4. Open Claude Desktop, authenticate with your Word + PIN
5. Query your health data

### Option C: MCP Advanced (Developers)

1. Install the VytalLink app and connect your health source

2. Install the MCP server:
   ```bash
   npm install -g @xmartlabs/vytallink-mcp-server
   ```

3. Configure your MCP client:

   **Claude Desktop** (`~/Library/Application Support/Claude/claude_desktop_config.json`):
   ```json
   {
     "mcpServers": {
       "vytalLink": {
         "command": "npx",
         "args": ["@xmartlabs/vytallink-mcp-server"]
       }
     }
   }
   ```

   **VS Code** (`~/.config/Code/User/mcp.json`):
   ```json
   {
     "servers": {
       "vytalLink": {
         "command": "npx",
         "args": ["@xmartlabs/vytallink-mcp-server"]
       }
     }
   }
   ```

   Also works with **Cursor** and other MCP-compatible clients.

4. Restart your client and authenticate with your Word + PIN

## Practical Example

**Scenario**: You're building a hackathon project that analyzes sleep quality and its correlation with daily activity.

**Input** (natural language via AI assistant):
> "Give me my sleep data and step counts for the last 7 days"

**Output**: The AI assistant retrieves your real sleep metrics (duration, phases) and step counts from your connected wearable via VytalLink, ready to analyze, visualize, or feed into your application logic.

**Another example**:
> "Compare my resting heart rate on workout days vs rest days this month"

The AI pulls heart rate and workout data, then produces the comparison — no manual data export or API integration needed on your part.

## Quick Reference

| Aspect | Details |
|--------|---------|
| **Supported data** | Heart rate, sleep, steps, workouts, wellness trends |
| **Health sources** | Apple Health, Google Fit |
| **AI integrations** | ChatGPT (GPT), Claude Desktop, any MCP client |
| **Authentication** | Word + PIN (generated in mobile app) |
| **Protocols** | MCP, REST API, WebSocket, OAuth 2.0 |
| **Platforms** | iOS, Android |
| **npm package** | `@xmartlabs/vytallink-mcp-server` |
| **Setup time** | ~2 minutes |

## Limitations and Considerations

- **App must stay open**: The mobile app needs to remain active during AI conversations — data streams in real-time from the phone
- **No server-side storage**: Data stays on your device. This is great for privacy but means there's no persistent API you can poll independently — the phone is the data source
- **Data scope**: Limited to what Apple Health / Google Fit collect. If your wearable doesn't sync to these platforms, VytalLink can't access it
- **Healthcare compliance**: This is wellness/fitness data, not clinical-grade medical data. Don't use it for diagnostic purposes
- **Connectivity**: Requires active internet connection on both phone and desktop

## Resources

- [VytalLink Website](https://vytallink.xmartlabs.com/)
- [MCP Setup Guide](https://vytallink.xmartlabs.com/mcp-setup.html)
- [iOS App](https://apps.apple.com/) / [Android App](https://play.google.com/)
- [Blog: Introducing VytalLink — Making Real Sense of Your Wearable Data](https://blog.xmartlabs.com/blog/vytallink-app/)
- [Blog: Build a Local Health Data Server on Your Phone with Flutter + MCP](https://blog.xmartlabs.com/blog/blog-building-health-apps-mcp-llms/)

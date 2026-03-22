# MCP HTTP Server (TypeScript)

This repository contains a scaffolded TypeScript MCP (Model Context Protocol) HTTP server using the @modelcontextprotocol/sdk. It includes an Express-based StreamableHTTP transport, client probes, and example tool-call scripts.

Quickstart

1. Install dependencies

   npm install

2. Start the dev server

   npm run dev    # or: npx tsx src/server.ts

3. Probe the server (initialize -> ping)

   npx tsx scripts/probe-mcp.ts

4. Call the example 'echo' tool

   npx tsx scripts/call-echo.ts

5. Run the MCP Inspector (installed globally to avoid zod conflicts)

   npm install -g @modelcontextprotocol/inspector
   mcp-inspector

Notes

- The Inspector was installed globally to avoid mixed zod versions; see MCP_SETUP.md and MCP_DETAILED_SUMMARY.md for more detail.
- For stateful StreamableHTTP transport: initialize() must be called once per session. Use DELETE /mcp to terminate a session before re-initializing.
- Ensure client requests set the correct Accept and Content-Type headers as documented in MCP_DETAILED_SUMMARY.md.

Key files

- src/server.ts            — Express server + StreamableHTTPServerTransport
- scripts/probe-mcp.ts    — Client probe (initialize -> ping)
- scripts/call-echo.ts    — Example tools/call client
- MCP_SETUP.md             — Setup & troubleshooting notes
- MCP_DETAILED_SUMMARY.md  — Detailed engineering summary (auto-generated)

Contributing

PRs welcome. For major changes, open an issue first to discuss scope.

License

MIT

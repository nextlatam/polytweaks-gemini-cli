# Polytweaks extension

For requests involving the user's Polytweaks model library, activate the bundled `polytweaks` skill and use the `polytweaks` MCP server. Tool names may be prefixed `mcp_polytweaks_`. Do not use the extension for unrelated local modeling unless the user asks to use Polytweaks.

Each user connects their own account with `/mcp auth polytweaks`. Account authentication happens in the browser; never collect passwords, API keys or tokens in chat. A successful model listing, including an empty library, verifies the account connection.

The MCP server exposes model/version, feedback and sharing operations. It does not install Blender or provide an embedded viewer or a local-file uploader. Use real authoring tools when present, exact returned viewer links, and the documented web-upload fallback when local files lack an accepted direct HTTPS URL. Preserve the user's requested scope and the CLI's permission prompts.

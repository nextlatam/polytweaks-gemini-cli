# Polytweaks for Gemini CLI

Work with your Polytweaks 3D model library from Gemini CLI: find models, preserve versions, retrieve sources, review feedback and create requested viewer, review or AR links. Each user signs in to their own Polytweaks account. The extension includes a workflow skill and a remote MCP connection.

The Polytweaks backend is live. On 2026-10-25 UTC, a dedicated HTTP runner completed real browser OAuth consent and successfully exercised all ten MCP tools with the registered public client. A real Gemini CLI session remains unverified: the owner deferred that test after official individual Google sign-in was refused. This package is not submitted for Gemini CLI gallery discovery, and backend acceptance does not imply gallery approval or native CLI compatibility.

[Gemini setup guide](https://www.polytweaks.com/help/gemini/) · [Public package source](https://github.com/nextlatam/polytweaks-gemini-cli).

## Install and connect

For a local review, extract this archive to a directory named `polytweaks`, then run:

```sh
gemini extensions install /absolute/path/to/polytweaks
```

For the public candidate source, use `gemini extensions install https://github.com/nextlatam/polytweaks-gemini-cli`. With a currently supported Gemini CLI authentication option, restart the CLI session, inspect `/extensions list` and `/skills list`, then run `/mcp auth polytweaks`. Sign in to Polytweaks in the browser and review the permissions. Ask: **“Use Polytweaks to list my models.”** An empty library is a valid connection. These are installation instructions; the native CLI end-to-end test remains deferred.

The extension's public OAuth profile is:

| Setting | Value |
| --- | --- |
| MCP endpoint | `https://api.polytweaks.com/gemini/mcp` |
| Client ID | `polytweaks-gemini` |
| Registered callback | `http://127.0.0.1:8787/oauth/callback` |

The callback is a local browser return address, not a public service. Its fixed port must be available. No Polytweaks API key, shared secret or service credential is required. Your own Gemini CLI authentication and usage allowance are separate.

Google ended consumer Gemini CLI “Login with Google” access on June 18, 2026; check your current supported CLI account/provider. This extension is for Gemini CLI, not the Gemini chat app or Antigravity. [Google account availability](https://developers.google.com/gemini-code-assist/docs/deprecations/code-assist-individuals).

## What backend acceptance verified

The live HTTP runner checked OAuth discovery, callback state/issuer, S256 PKCE and all ten tools. One controlled cube retained exactly three versions; replaying the first save with identical inputs created no duplicate. It checked private model/file access, comments, five-minute view/review links with downloads disabled, and a five-minute AR link. Gemini credentials were rejected by the Claude resource; refresh invalidated the previous access token, and revocation was followed by HTTP 401.

The test used public controlled GLB fixtures. It did not prove native local-file/chat-attachment transfer, original Blender or authored USDZ transfer, QR rendering, device AR, or an in-host Gemini session. Missing companions and the iOS AR limitation were reported explicitly. Tokens and capability URLs were excluded from the recorded evidence. Installation and skill discovery in the official CLI were checked separately from these backend calls.

## Models and files

Use real authoring tools already available on your computer. The extension does not install Blender, generate models itself or embed a viewer. Open returned Polytweaks web links to inspect saved models.

Keep the actual editable source, matching GLB and authored USDZ together; Blender sources should pack their resources. A conversion is labeled as a conversion. Saves append a version to an existing model when requested, preserving earlier versions.

The MCP accepts actual direct HTTPS file URLs on configured hosts; it cannot read local paths. If no accepted URL is available, upload the local files in the Polytweaks website and then retrieve the saved model through the connector. It does not publish files or create tunnels automatically. Missing source/USDZ files and save errors remain explicit.

Shares are created only when requested. View-only and commentable review links are distinct; downloads are disabled unless requested. Public links expire. Creation of a link does not send it to anyone.

## Account access and support

The connector requests model read/write, comment read/write and share creation scopes. Revoke the Gemini connection in Polytweaks to remove server access; uninstalling the extension alone does not revoke the grant. Never paste passwords or tokens into a prompt.

[Polytweaks](https://www.polytweaks.com/) · [Support](https://www.polytweaks.com/public/faq/) · [Privacy](https://www.polytweaks.com/privacy/) · [Terms](https://www.polytweaks.com/terms-and-conditions/)

This bundle contains no executable hooks, private configuration or credentials. Its MCP actions retain Gemini CLI's normal confirmation controls.

## License

The extension's distributed instructions, metadata and supporting package files are provided under the included MIT license. That license does not cover the Polytweaks backend, hosted service, customer models or other user content, and does not grant trademark rights.

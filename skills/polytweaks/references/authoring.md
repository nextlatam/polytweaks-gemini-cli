# Authoring, revisions and file transfer

## Work with the real model

Resolve the model and selected version before editing. `get_model_files` returns expiring downloads for files already saved to that version. Fetch a new result if those links expire; do not guess storage paths. The existence of a source download does not establish Gemini's ability to download, modify or transfer the file back.

When Blender or another authoring environment is actually available, preserve original inputs and disable script auto-execution for untrusted source files. Make the requested changes, inspect the result and export matching deliverables. A Blender-authored model should keep an editable `.blend` with packed resources, a GLB for the web viewer, and a separately authored USDZ for iOS AR. Include other real authoring sources in the user's handoff when relevant; do not label a Blender conversion as the original authoring source.

For a feedback revision, read the selected version's actual comments and use spatial/camera context when provided. Apply only the requested scope. If the environment cannot author or export the model, retain the selected version and prepare a concise editing brief; do not pretend to have generated files.

If the user requests a preview before saving, show an available render/output or authoring preview and stop there. Gemini's Polytweaks connector does not expose `preview_model` or an embedded 3D widget. A website viewer URL for an existing saved model is not a new unsaved preview.

## Transfer and preserve files

The current `save_model` file descriptor is:

```json
{
  "download_url": "<actual direct HTTPS file URL accepted by the server>",
  "file_name": "model.glb",
  "mime_type": "model/gltf-binary"
}
```

Use that shape for `glb` and the optional `blend`, `usdz` and `thumbnail`. It illustrates the schema, not a usable URL. Consult the tool for current limits. A server request must be able to fetch the bytes without a browser session, and the host must be on the administrator's exact allowlist. Do not infer that a Google URL or an uploaded Gemini attachment meets those requirements. Do not request a user's cookies or session tokens.

Supply a real PNG/WebP render of the finished model as `thumbnail` when available. A reference photo is not a model render. A missing thumbnail need not block an authorized save; the connected web viewer can generate one after loading. Do not claim a headless save rendered it.

If no accepted URL exists, use the normal Polytweaks web upload flow with the user's files. After the user completes the upload, retrieve the model/version through MCP to confirm it. Browser upload and Gemini attachment transfer are different capabilities.

Preserve source and companion files in the same saved version whenever available. If the response confirms only the GLB, report the attachment warning and missing deliverable; do not repeat the entire save under a new operation key. Use the website's version controls for an unsupported companion-file action rather than inventing a tool.

## File quality when relevant

Offer brief size/quality advice when it would help the requested delivery; do not block a save with an optimization checklist or edit files without a request. Base claims on measured files. Draco can reduce geometry transfer; appropriately sized PNG/JPEG textures reduce texture bytes. Avoid recompressing already compressed geometry. Preserve silhouette, labels, animation, materials and scale when optimizing.

Keep PNG/JPEG textures and a portable geometry export for native AR, plus an authored USDZ for iOS. KTX2 is an optional web variant and does not establish native AR compatibility. Do not promise target-device behavior without testing. Missing USDZ must remain explicit when the user needs iOS AR.

Creation/editing alone is not permission to persist, while an existing request to create/edit and save is sufficient. A saved revision appends to the existing `assetId` and preserves earlier versions.

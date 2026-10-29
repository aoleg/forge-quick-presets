# Changelog

## 0.1.1 - 2026-10-29

- Stopped saving layout blocks (rows, columns, groups, plain accordions), the output panel and hidden textboxes as preset fields. Each of them repeated the value of the first field inside it.
- Added Aspect Ratio Helper support: the selected ratio (including a swapped orientation), `Side` and `Align to a multiple of 64` are saved and restored together with Width and Height.
- Width and Height are now set after the aspect ratio, so the helper no longer recalculates one side from the other during apply.
- Reset now returns the Aspect Ratio Helper to `Off` and to its configured `Side` and `Align to a multiple of 64` defaults. Before, Reset cleared the align box.
- Presets saved by 0.1.0 still apply: their Aspect Ratio Helper wrapper fields are read as the new fields, and their layout and output panel fields are skipped.
- Fixed the Forge preset baseline ids for Hires steps and Hires Distilled CFG Scale, which made those fields look changed in every preset.
- Stopped saving search boxes, such as the LoRA tab filter, as preset fields.

## 0.1.0 - 2026-04-29

Stable local version.

- Added delta quick presets for txt2img/img2img UI fields.
- Added apply, reset, delete, save changed, and update selected preset flows.
- Preserved user-provided images, masks, galleries, uploads, prompts, checkpoints, VAE/Text Encoder, and native Forge UI preset selectors.
- Added ControlNet support for enable state, model, preprocessor, weights, timestep range, sliders, checkboxes, and radio fields.
- Treated ControlNet `Control Type` as a transient filter: quick presets apply through `All` instead of saving Tile/Instant-ID/Style filter state.
- Improved dropdown application so Gradio internal values are updated, not just visible text.
- Hid programmatic dropdown option lists to avoid large visual flashes and page layout jumps.
- Preserved scroll position during apply/reset, including ControlNet and Scripts presets.
- Added `Update` to overwrite the selected preset with the current changed fields.
- Limited `user_presets.json.bak-*` retention to the latest three backups.

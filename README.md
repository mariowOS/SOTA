# mariowOS SOTA packages

`version.json` is a flat map of SOTA-managed system components to their
installed package version. Increment only the component version(s) whose files
are changing. ACode, Tiles, Weather, and Sandbox are maintained in their own
repositories and are not updated by SOTAs.

Package files are stored in folders at the repository root:

- Each SOTA-managed system app folder (`settings/`, etc.) maps to
  `system/desktop/apps/<name>/`.
- `feedback/` maps to `system/desktop/fallback/apps/feedback/`.
- `desktop/` maps to `system/desktop/`, excluding `apps/` and
  `fallback/apps/feedback/` because those paths have their own packages.

For example, `settings/index.html` updates the Settings app's `index.html`.
SOTAs verify every package file before installation and overlay included files;
they do not delete local files omitted from a package. `config.json` files are
never installed. User-specific state such as `desktop/notes-db.json`,
`desktop/assets/avatar.user.png`, and `desktop/assets/wallpaper.user.png` is
not included in the desktop package. The desktop package also excludes
`desktop/assets/icons/wallpaper.user.jpg`.

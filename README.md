# Obsidian Link Extractor Plugin

This plugin for Obsidian (https://obsidian.md) extracts content from external links in the current file and saves it as separate markdown files.

## Features

- Scans the current file for external links
- Extracts the main content from each linked webpage
- Saves the extracted content as individual markdown files in your vault

## How to use

1. Open a note containing external links
2. Run the "Extract Links" command from the command palette
3. The plugin will process each link and create new markdown files with the extracted content

## Installation

### From within Obsidian

1. Open Settings > Community plugins
2. Make sure Safe mode is off
3. Click Browse community plugins
4. Search for "Link Extractor"
5. Click Install
6. Once installed, close the community plugins window and activate the newly installed plugin

### Manual installation

1. Download `main.js`, `styles.css`, `manifest.json` from the latest release
2. Create a new folder in your vault's plugins folder: `VaultFolder/.obsidian/plugins/obsidian-link-extractor/`
3. Copy the downloaded files into this folder
4. Reload Obsidian
5. If prompted about Safe Mode, you can disable safe mode and enable the plugin.
   Otherwise, head to Settings, third-party plugins, make sure safe mode is off and
   enable the plugin from there.

## Development

This plugin uses TypeScript to provide type checking and documentation.
The repo depends on the latest plugin API (obsidian.d.ts) in Typescript Definition format, which contains TSDoc comments describing what it does.

### Releasing new releases

- Update your `manifest.json` with your new version number, such as `1.0.1`, and the minimum Obsidian version required for your latest release.
- Update your `versions.json` file with `"new-plugin-version": "minimum-obsidian-version"` so older versions of Obsidian can download an older version of your plugin that's compatible.
- Create new GitHub release using your new version number as the "Tag version". Use the exact version number, don't include a prefix `v`. See here for an example: https://github.com/obsidianmd/obsidian-sample-plugin/releases
- Upload the files `main.js`, `manifest.json`, `styles.css` as binary attachments. Note: The manifest.json file must be in two places, first the root path of your repository and also in the release.
- Publish the release.

> You can simplify the version bump process by running `npm version patch`, `npm version minor` or `npm version major` after updating `minAppVersion` manually in `manifest.json`.
> The command will bump version in `manifest.json` and `package.json`, and add the entry for the new version to `versions.json`

### Adding your plugin to the community plugin list

- Check https://github.com/obsidianmd/obsidian-releases/blob/master/plugin-review.md
- Publish an initial version.
- Make sure you have a `README.md` file in the root of your repo.
- Make a pull request at https://github.com/obsidianmd/obsidian-releases to add your plugin.

### API Documentation

See https://github.com/obsidianmd/obsidian-api
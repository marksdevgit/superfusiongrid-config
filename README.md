# SuperFusionGrid Remote Configuration

This repository contains the remote configuration for the SuperFusionGrid iOS app.

## Configuration File

**`config.json`** - Contains app configuration that can be updated without requiring an app update.

### Structure

```json
{
  "movesBeforeAd": 75
}
```

### Fields

- **movesBeforeAd** (integer): Number of moves a player makes before an interstitial ad is shown. Default: 75

## Usage

The SuperFusionGrid app fetches this configuration on launch and caches it locally. If the remote config is unavailable, the app falls back to the default value of 75.

**Config URL:** `https://raw.githubusercontent.com/marksdevgit/superfusiongrid-config/main/config.json`

## Updating Configuration

1. Edit `config.json` in this repository
2. Commit and push changes to the `main` branch
3. The app will fetch the new configuration on next launch (or after cache expires)

## Notes

- Configuration is cached for 24 hours
- Changes take effect on app restart
- Invalid JSON or network errors will cause fallback to defaults
- The app validates that `movesBeforeAd` is between 1 and 500

## Version History

- **2025-12-10**: Initial configuration with movesBeforeAd = 75

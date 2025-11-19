# Documentation: tauri.conf.json

## File Metadata

- **File Path**: `src-tauri/tauri.conf.json`
- **Size**: 1,226 bytes
- **Lines**: 55
- **Words**: 88
- **Extension**: `.json`
- **Type**: JSON data/configuration file

## Original Source

```json
{
  "$schema": "https://schema.tauri.app/config/2",
  "productName": "Open CoreUI Desktop",
  "version": "0.9.6",
  "identifier": "com.github.xxnuo.ocd",
  "mainBinaryName": "Open CoreUI Desktop",
  "build": {
    "beforeDevCommand": "",
    "beforeBuildCommand": "",
    "frontendDist": "./static"
  },
  "app": {
    "withGlobalTauri": true,
    "windows": [
      {
        "title": "Open CoreUI Desktop",
        "width": 1440,
        "height": 900
      }
    ],
    "security": {
      "csp": null
    }
  },
  "bundle": {
    "active": true,
    "createUpdaterArtifacts": true,
    "targets": [
      "deb",
      "rpm",
      "app",
      "dmg",
      "nsis",
      "msi"
    ],
    "externalBin": [
      "../bin/open-coreui"
    ],
    "icon": [
      "icons/32x32.png",
      "icons/128x128.png",
      "icons/128x128@2x.png",
      "icons/icon.icns",
      "icons/icon.ico"
    ]
  },
  "plugins": {
    "updater": {
      "pubkey": "dW50cnVzdGVkIGNvbW1lbnQ6IG1pbmlzaWduIHB1YmxpYyBrZXk6IEI5QjA0MTk2NjE3QjA0MzIKUldReUJIdGhsa0d3dWJ0YklGeWdIRzR0QkJkU2lWejdxdzJaY0cyc2JLa2RPd3ZxdVd3dEpadXgK",
      "endpoints": [
        "https://github.com/xxnuo/open-coreui/releases/latest/download/latest.json"
      ]
    }
  }
}
```

## High-Level Overview

This configuration file defines structured settings for the application.

**Purpose**: Configuration data in JSON format.

**Usage**: Loaded by the application or build system to configure behavior.


## Detailed Walkthrough

### Configuration Structure

This configuration file contains 55 lines of structured data defining application settings, dependencies, or metadata.


## Key Components

### Configurations

- `active`
- `app`
- `beforeBuildCommand`
- `beforeDevCommand`
- `build`
- `bundle`
- `createUpdaterArtifacts`
- `csp`
- `endpoints`
- `externalBin`
- `frontendDist`
- `height`
- `https`
- `icon`
- `identifier`
- `mainBinaryName`
- `plugins`
- `productName`
- `pubkey`
- `security`
- *(and 7 more)*



## Usage Examples

*Usage examples depend on the application context.*


## Performance & Security Notes

*No specific performance or security concerns identified.*


## Related Files

- **Same Directory**: 4 related files in `src-tauri/`
- **Parent Directory**: `src-tauri/`

## Testing & Execution

*Testing information not applicable for this file type.*


---

*Generated: 2025-11-19T02:08:05.518944*
*Source: `src-tauri/tauri.conf.json`*
*Repository: http://local_proxy@127.0.0.1:46101/git/raminpapo/open-coreui*
*Commit: 9668d1c1*

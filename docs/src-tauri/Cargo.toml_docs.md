# Documentation: Cargo.toml

## File Metadata

- **File Path**: `src-tauri/Cargo.toml`
- **Size**: 985 bytes
- **Lines**: 33
- **Words**: 133
- **Extension**: `.toml`
- **Type**: TOML configuration file

## Original Source

```toml
[package]
name = "open-coreui-desktop"
version = "0.9.6"
description = "Open CoreUI Desktop Application"
authors = ["xxnuo"]
edition = "2021"

# See more keys and their definitions at https://doc.rust-lang.org/cargo/reference/manifest.html

[lib]
# The `_lib` suffix may seem redundant but it is necessary
# to make the lib name unique and wouldn't conflict with the bin name.
# This seems to be only an issue on Windows, see https://github.com/rust-lang/cargo/issues/8519
name = "open_coreui_desktop_lib"
crate-type = ["staticlib", "cdylib", "rlib"]

[build-dependencies]
tauri-build = { version = "2", features = [] }

[dependencies]
tauri = { version = "2", features = [] }
tauri-plugin-opener = "2"
serde = { version = "1", features = ["derive"] }
serde_json = "1"
portpicker = "0.1.1"
tauri-plugin-shell = "2.3.1"
tauri-plugin-http = "2.5.2"
tauri-plugin-websocket = "2"

[target.'cfg(not(any(target_os = "android", target_os = "ios")))'.dependencies]
tauri-plugin-updater = "2"


```

## High-Level Overview

This TOML configuration file defines project settings and dependencies.

**Purpose**: Configuration and metadata for the Rust/Tauri application.

**Contents**:
- Project metadata and build configuration
- Dependency declarations
- Feature flags and build settings


## Detailed Walkthrough

### Configuration Structure

This configuration file contains 33 lines of structured data defining application settings, dependencies, or metadata.


## Key Components

*No specific components identified.*


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

*Generated: 2025-11-19T02:08:05.501266*
*Source: `src-tauri/Cargo.toml`*
*Repository: http://local_proxy@127.0.0.1:46101/git/raminpapo/open-coreui*
*Commit: 9668d1c1*

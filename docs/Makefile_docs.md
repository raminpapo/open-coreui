# Documentation: Makefile

## File Metadata

- **File Path**: `Makefile`
- **Size**: 2,801 bytes
- **Lines**: 71
- **Words**: 280
- **Extension**: `none`
- **Type**: File (no extension)

## Original Source

```
.PHONY: build-backend build-backend-slim build-desktop build-frontend build-frontend-svelte prepare-backend prepare-desktop prepare-frontend prepare-frontend-svelte prepare-git run-backend run-backend-slim run-desktop

BUILD_HOST := $(shell rustc -Vv | grep host | cut -d' ' -f2)

prepare-git:
	git submodule update --init --recursive
	mkdir -p build

prepare-frontend:
	cd backend && bun install

prepare-frontend-svelte:
	cd backend/svelte-frontend && bun install

prepare-backend:
	cd backend && bun install
	cd backend/rust-backend && cargo fetch

prepare-desktop:
	cd src-tauri && cargo fetch

build-frontend: prepare-frontend
	cd backend && bun run build

build-frontend-svelte: prepare-frontend-svelte
	cd backend/svelte-frontend && bun run build

# backend/rust-backend/src/static_files.rs
build-backend: build-frontend-svelte
	cd backend/rust-backend && cargo build --release
	mkdir -p bin
	cp backend/rust-backend/target/release/open-webui-rust bin/open-coreui-${BUILD_HOST}

# Without static frontend
build-backend-slim:
	cd backend/rust-backend && cargo build --release --no-default-features
	mkdir -p bin
	cp backend/rust-backend/target/release/open-webui-rust bin/open-coreui-slim-${BUILD_HOST}

# Without static frontend
run-backend-slim:
	cd backend/rust-backend && cargo run --no-default-features

run-backend:
	cd backend/rust-backend && cargo run

run-desktop:
	cargo tauri dev

build-desktop:
	cargo tauri build

update-version:
	@echo "Current version: $$(grep '^version = ' src-tauri/Cargo.toml | head -1 | sed 's/version = "\(.*\)"/\1/')"
	@read -p "Enter new version (default: $$(grep '^version = ' src-tauri/Cargo.toml | head -1 | sed 's/version = "\(.*\)"/\1/')): " NEW_VERSION; \
	NEW_VERSION=$${NEW_VERSION:-$$(grep '^version = ' src-tauri/Cargo.toml | head -1 | sed 's/version = "\(.*\)"/\1/')}; \
	echo "Updating to version: $$NEW_VERSION"; \
	sed -i.bak "s/^version = \".*\"/version = \"$$NEW_VERSION\"/" src-tauri/Cargo.toml && rm src-tauri/Cargo.toml.bak; \
	sed -i.bak "s/\"version\": \".*\"/\"version\": \"$$NEW_VERSION\"/" src-tauri/tauri.conf.json && rm src-tauri/tauri.conf.json.bak; \
	echo sed -i.bak "s/\"version\": \".*\"/\"version\": \"0.6.32-$$NEW_VERSION\"/" backend/package.json && echo rm backend/package.json.bak; \
	echo sed -i.bak "s/\"version\": \".*\"/\"version\": \"0.6.32-$$NEW_VERSION\"/" backend/svelte-frontend/package.json && echo rm backend/svelte-frontend/package.json.bak; \
	sed -i.bak "s/^version = \".*\"/version = \"$$NEW_VERSION\"/" backend/rust-backend/Cargo.toml && rm backend/rust-backend/Cargo.toml.bak; \
	sed -i.bak "s/^pkgver=.*/pkgver=$$NEW_VERSION/" PKGBUILD && rm PKGBUILD.bak; \
	echo "Version updated successfully to $$NEW_VERSION"

build-arch-pkg: build-backend
	makepkg -f

update-aur:
	makepkg --printsrcinfo > .SRCINFO

```

## High-Level Overview

This file is part of the open-coreui project infrastructure.

**Purpose**: Project infrastructure or build configuration

**Role**: Supporting file for the application's build, deployment, or functionality.


## Detailed Walkthrough

### File Structure

This file contains 71 lines.

*Detailed analysis available in the source code section above.*


## Key Components

### Identifiers

- `BUILD_HOST`
- `Cargo`
- `Current`
- `Enter`
- `NEW_VERSION`
- `PHONY`
- `PKGBUILD`
- `SRCINFO`
- `Updating`
- `Version`
- `Without`
- `arch`
- `backend`
- `build`
- `cargo`
- `conf`
- `coreui`
- `default`
- `desktop`
- `echo`
- *(and 35 more)*



## Usage Examples

*Usage examples depend on the application context.*


## Performance & Security Notes

*No specific performance or security concerns identified.*


## Related Files

- **Same Directory**: 11 related files in `./`

## Testing & Execution

*Testing information not applicable for this file type.*


---

*Generated: 2025-11-19T02:08:05.484380*
*Source: `Makefile`*
*Repository: http://local_proxy@127.0.0.1:46101/git/raminpapo/open-coreui*
*Commit: 9668d1c1*

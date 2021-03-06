# rust-sandbox

## Settings

- [install C++ Build Tools](https://visualstudio.microsoft.com/ja/visual-cpp-build-tools/)
  - or [Microsoft Visual Studio](https://visualstudio.microsoft.com/ja/downloads/)
- [install Rust](https://www.rust-lang.org/tools/install)
- install `rust-analyzer` by Visual Studio MarketPlace
- setup rust-analyzer

```bash
rustup component add rust-src
rustup component add rust-analysis
rustup component add rls
```

## Hello World!

- `$ cargo new hello_world`
- `$ cd hello_world/src`
- `$ rustc main.rs`
- `$ ./main`

```bash
Hello, world!
```

- `$ cargo run`

## Version

- Dockerfile
  - [Tag list](https://mcr.microsoft.com/v2/vscode/devcontainers/rust/tags/list)
  - [Update example](https://github.com/microsoft/vscode-dev-containers/blob/main/containers/rust/history/0.201.4.md)

```Dockerfile
ARG VARIANT="buster"
FROM mcr.microsoft.com/vscode/devcontainers/rust:0-${VARIANT}
```

## Remote Container

**Admin**

- Open command palette
  - `Remote-Containes: Add Development Container Configuration Files...`
  - `Rust`
  - `buster`
    - [x] GitHub CLI

**Developers**

- Open a Remote Window
  - Add Proxy config to `.devcontainer/devcontainer.json`

```json
	"build": {
		"dockerfile": "Dockerfile",
		"args": {
			"VARIANT": "buster",
			"PROXY": "http://xxxx:8080" // here
		}
	},
```

- Reopen in Container

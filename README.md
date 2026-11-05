# NES Emulator

[![Rust CI](https://github.com/riccardoie/nes_emulator/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/riccardoie/nes_emulator/actions/workflows/ci.yml)

A Nintendo Entertainment System (NES) emulator project written in Rust.

## Status

Early development. The repository currently contains the Rust application scaffold and CI checks. NES emulation is not implemented yet; running the application prints `Hello, world!`.

## Getting started

Install the latest stable [Rust toolchain](https://rustup.rs/). This project uses Rust edition 2024, which requires Rust 1.85 or newer.

```sh
git clone https://github.com/riccardoie/nes_emulator.git
cd nes_emulator
cargo run --locked
```

Build an optimized executable:

```sh
cargo build --release --locked
```

## Development

- `main`: stable branch; changes are merged through pull requests.
- `dev`: integration branch; direct pushes are allowed.

Run the same checks used by CI before opening a pull request:

```sh
cargo fmt --all -- --check
cargo clippy --locked --all-targets --all-features -- -D warnings
cargo test --locked --all-targets --all-features
```

To apply formatting, run `cargo fmt --all`. There are no tests yet.

GitHub Actions runs these checks on pushes and pull requests targeting `main` or `dev`.

## Proposed roadmap

- [ ] Cartridge loading and iNES header parsing
- [ ] CPU instruction execution and tests
- [ ] Memory bus and cartridge mapping
- [ ] PPU and video output
- [ ] Controller input
- [ ] APU and audio output
- [ ] Timing and compatibility improvements

## ROMs and save data

No game ROMs are included. Use only ROMs you are legally entitled to use, such as appropriately licensed homebrew or test ROMs.

The `.gitignore` excludes local `roms/` and `saves/` directories, along with `.nes`, `.fds`, `.sav`, and `.state` files. ROM loading and save support are not implemented yet.

## License

A license has not been selected yet. Public availability alone does not grant permission to use, modify, or redistribute the code.

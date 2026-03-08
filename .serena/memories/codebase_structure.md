# Codebase Structure

## Top-Level
```
Amethyst/              - Main app source code
AmethystTests/         - Unit tests
Amethyst.xcodeproj/    - Xcode project
Amethyst.xcworkspace/  - Xcode workspace (use this for building)
docs/                  - Documentation (troubleshooting, config files, custom layouts)
fastlane/              - Fastlane config (Fastfile, Gymfile, Appfile)
.github/               - GitHub Actions CI, issue templates
```

## App Source (`Amethyst/`)
- **AppDelegate.swift** / **main.swift** — App entry point
- **Layout/** — Layout engine
  - `Layout.swift` — Base `Layout` class, `StatefulLayout`, `PanedLayout` protocol
  - `ReflowOperation.swift` — Window reflow logic
  - `Layouts/` — Individual layout implementations (TallLayout, WideLayout, FullscreenLayout, BSPLayout, ColumnLayout, RowLayout, FloatingLayout, ThreeColumnLayout, FourColumnLayout, CustomLayout, etc.)
- **Managers/** — Core management layer
  - `WindowManager.swift` — Central window management, event handling, transitions
  - `ScreenManager.swift` — Per-screen layout management
  - `AppManager.swift` — Application tracking
  - `Windows.swift` / `Screens.swift` — Window/screen collection management
  - `HotKeyRegistrar.swift` — Hotkey registration
  - `FocusFollowsMouseManager.swift` — Mouse-driven focus
  - `WindowTransitionCoordinator.swift` / `FocusTransitionCoordinator.swift` — Transition handling
  - `LayoutType.swift` — Layout type registry
  - `LogManager.swift` — Logging
- **Model/** — Data models
  - `Window.swift` — `WindowType` protocol, `AXWindow` class (Accessibility-based window)
  - `Application.swift` — `ApplicationType` protocol, `AnyApplication`
  - `Screen.swift`, `Space.swift` — Screen/space models
  - `CGInfo.swift` — Core Graphics info
  - `MouseState.swift` — Mouse tracking state
  - `Change.swift`, `Reliability.swift` — Change tracking
  - `ApplicationObservation.swift` / `ApplicationEventHandler.swift` — App event handling
- **Preferences/** — Settings UI and configuration
  - `UserConfiguration.swift` — Config model (`ConfigurationKey`, `CommandKey`, `FloatingBundle`)
  - Various `*PreferencesViewController.swift` + `.xib` files for preferences panels
- **Events/** — Event handling
  - `HotKeyManager.swift` — Keyboard shortcut management
- **View/** — UI components
  - `PreferencesWindow.swift`, `LayoutNameWindow.swift` / `.xib`
- **Categories/** — Swift extensions
  - `NSRunningApplication+Manageable.swift`, `NSTableView+Amethyst.swift`
- **Debug/** — Debug information views
  - `DebugInfo.swift`, `WindowsInfo.swift`, `ScreensInfo.swift`, `AppsInfo.swift`

## Tests (`AmethystTests/`)
- `Tests/Layout/` — Layout-specific tests (one per layout type)
- `Tests/Configuration/` — UserConfiguration tests
- `Tests/Managers/` — HotKeyManager, ScreenManager tests
- `Tests/Categories/` — Extension tests
- `Helpers/` — Test helpers

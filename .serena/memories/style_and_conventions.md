# Code Style and Conventions

## Language & Version
- Swift (modern syntax, protocols, generics, extensions)
- Objective-C bridging for some low-level macOS APIs (Accessibility, CoreGraphics)

## Naming
- **Classes**: PascalCase (e.g., `WindowManager`, `ScreenManager`, `AXWindow`)
- **Protocols**: PascalCase with `Type` or `Delegate` suffix (e.g., `WindowType`, `ApplicationType`, `ScreenManagerDelegate`)
- **Functions/Methods**: camelCase
- **Variables/Properties**: camelCase
- **Enums**: PascalCase for type, camelCase for cases

## SwiftLint Rules (`.swiftlint.yml`)
- Line length warning: 200 chars (ignores comments)
- Cyclomatic complexity limit: 15
- Large tuple limit: 3
- Nesting type level: 2
- Disabled rules: `function_body_length`, `closing_brace`, `statement_position`, `force_cast`, `force_try`, `no_space_in_method_call`, `file_length`, `type_body_length`
- Excluded identifier names: `id`
- Included paths: `Amethyst/`, `AmethystTests/`

## Architecture Patterns
- **Protocol-oriented design**: Core types are protocols (`WindowType`, `ApplicationType`, `PanedLayout`, `ConfigurationStorage`)
- **Delegate pattern**: Used extensively (`ScreenManagerDelegate`, `UserConfigurationDelegate`, `ApplicationObservationDelegate`)
- **Extensions via namespaces**: Related functionality grouped in `// MARK:` extensions on classes
- **Categories**: Swift extensions on system types in `Categories/` directory

## Contributing Guidelines
- Branch off `development` for PRs
- Stick to the general style of existing code

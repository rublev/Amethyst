# Suggested Commands

## Setup
```bash
brew bundle                # Install dependencies (fastlane, xcbeautify, swiftlint)
```

## Building
```bash
# Build via Fastlane (produces ./build/Amethyst.app)
fastlane mac

# Build via xcodebuild
xcodebuild -workspace Amethyst.xcworkspace -scheme Amethyst build
```

## Testing
```bash
# Run all tests (CI command)
set -o pipefail && xcodebuild -workspace Amethyst.xcworkspace -scheme Amethyst clean test | xcbeautify

# Run tests without cleaning
set -o pipefail && xcodebuild -workspace Amethyst.xcworkspace -scheme Amethyst test | xcbeautify

# Run a specific test class
set -o pipefail && xcodebuild -workspace Amethyst.xcworkspace -scheme Amethyst test -only-testing:AmethystTests/TallLayoutTests | xcbeautify
```

## Linting
```bash
swiftlint                  # Run SwiftLint on the project
swiftlint --fix            # Auto-fix linting issues
```

## Git
```bash
git checkout development   # Main dev branch
# PRs should target `development`, not `master`
```

## System (Darwin/macOS)
```bash
open Amethyst.xcworkspace  # Open in Xcode
```

# Task Completion Checklist

When a coding task is completed, ensure:

1. **Linting**: Run `swiftlint` and fix any issues
2. **Testing**: Run tests with `set -o pipefail && xcodebuild -workspace Amethyst.xcworkspace -scheme Amethyst test | xcbeautify`
3. **Build verification**: Ensure the project builds without errors
4. **Commit**: Commit to `development` branch with a short, non-verbose message
5. **Byte-sized commits**: Split changes into logical, atomic commits (per CLAUDE.md)

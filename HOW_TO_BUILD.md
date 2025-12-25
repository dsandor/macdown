# How to Build MacDown

## Prerequisites

- Xcode (with macOS SDK 10.14 or later)
- Bundler (Ruby gem manager)

## Build Steps

```bash
# 1. Initialize git submodules
git submodule update --init

# 2. Install Ruby dependencies (for CocoaPods)
bundle install

# 3. Install CocoaPods dependencies
bundle exec pod install

# 4. Build the custom markdown parser
make -C Dependency/peg-markdown-highlight

# 5. Open the workspace in Xcode
open MacDown.xcworkspace
```

Then in Xcode:

1. Select the **MacDown** scheme
2. Build with **Cmd+B** (or Product → Build)

**Important**: Use `MacDown.xcworkspace` (not `.xcodeproj`) since the project uses CocoaPods.

## Updating Dependencies

If you encounter build issues, update dependencies with:

```bash
git submodule update
bundle exec pod install
```

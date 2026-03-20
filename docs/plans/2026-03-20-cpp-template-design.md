# C++ Template Design

## Goal

Turn the VS Code CMake quick start scaffold into a reusable minimal C++ template that keeps source files organized and still works with the VS Code CMake Tools build and run buttons.

## Chosen Approach

Use a single executable project with a split `include/` and `src/` layout.

The shared project configuration remains simple:

- `CMakeLists.txt` defines one executable target
- `CMakePresets.json` remains generic and does not hard-code machine-specific compiler paths
- VS Code uses CMake Tools kit selection so the compiler can be chosen from the UI

## Structure

```text
cpp-template/
├── .vscode/
│   └── settings.json
├── include/
│   └── hello.h
├── src/
│   ├── hello.cpp
│   └── main.cpp
├── CMakeLists.txt
├── CMakePresets.json
├── .gitignore
└── README.md
```

## Design Notes

- Keep the template small: no tests, no extra subdirectories, no third-party dependencies.
- Fix the project name as `cpp-template` so copied projects can rename it explicitly later.
- Keep a single executable target to make the VS Code launch target unambiguous.
- Store VS Code settings in the repo so opening the template is enough to use configure, build, and run from the editor.
- Preserve a generic `CMakePresets.json` for CLI and future extension, but do not rely on it for compiler selection in VS Code.

## VS Code Workflow

- Open the folder in VS Code
- Run `CMake: Select a Kit`
- Choose a compiler
- Use the CMake Tools configure, build, and run actions

This avoids committing machine-specific compiler paths while keeping the editor workflow straightforward.

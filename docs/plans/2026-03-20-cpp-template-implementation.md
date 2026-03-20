# C++ Template Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Convert the starter scaffold into a reusable minimal C++ template that works cleanly with VS Code CMake Tools configure, build, and run actions.

**Architecture:** Use one executable target named `cpp-template` with source files under `src/` and public headers under `include/`. Keep shared CMake presets generic, and use VS Code kit selection for compiler choice so the repository does not contain machine-specific compiler paths.

**Tech Stack:** CMake, C++17, VS Code CMake Tools, VS Code C/C++

---

### Task 1: Create the template directory layout

**Files:**
- Create: `F:\Project\C++\tempelate\.vscode\settings.json`
- Create: `F:\Project\C++\tempelate\include\hello.h`
- Create: `F:\Project\C++\tempelate\src\hello.cpp`
- Create: `F:\Project\C++\tempelate\src\main.cpp`
- Modify: `F:\Project\C++\tempelate\README.md`
- Modify: `F:\Project\C++\tempelate\.gitignore`
- Delete: `F:\Project\C++\tempelate\main.cpp`

**Step 1: Add the missing directories and source files**

Create `.vscode/`, `include/`, and `src/`. Move the sample program into `src/main.cpp` and split reusable logic into `include/hello.h` and `src/hello.cpp`.

**Step 2: Add repository defaults**

Create `.gitignore` so build outputs and local user presets are not committed. Add `README.md` with a short explanation of the structure and workflow.

**Step 3: Verify the resulting tree**

Check that the project now matches the intended minimal template shape.

### Task 2: Update CMake for the new structure

**Files:**
- Modify: `F:\Project\C++\tempelate\CMakeLists.txt`
- Modify: `F:\Project\C++\tempelate\CMakePresets.json`

**Step 1: Rewrite the root `CMakeLists.txt`**

Define project `cpp-template`, set C++17, add the executable from `src/main.cpp` and `src/hello.cpp`, and add the `include/` directory to the target.

**Step 2: Replace machine-specific presets**

Rewrite `CMakePresets.json` so it contains generic debug and release presets without hard-coded compiler paths.

**Step 3: Align the editor workflow**

Configure VS Code settings so CMake Tools uses kit selection for compiler choice while still supporting configure, build, and run from the editor.

### Task 3: Verify the template on the current machine

**Files:**
- Verify: `F:\Project\C++\tempelate\CMakeLists.txt`
- Verify: `F:\Project\C++\tempelate\src\main.cpp`
- Verify: `F:\Project\C++\tempelate\src\hello.cpp`

**Step 1: Configure the project**

Run CMake with an available compiler on the current machine and verify configure succeeds.

**Step 2: Build the executable**

Build the generated project and confirm the executable is produced.

**Step 3: Run the executable**

Execute the sample program and confirm it prints the expected hello message.

**Step 4: Confirm VS Code instructions are documented**

Ensure the README explains how to choose a compiler in VS Code by using `CMake: Select a Kit`.

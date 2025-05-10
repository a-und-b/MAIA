# MAIA - Machine-Augmented Intelligence Architecture

This repository contains a reusable framework designed to enhance collaboration between human developers and Large Language Model (LLM) AI coding assistants in software development projects.

It provides a standardized starting point by including essential structures and guides to foster effective communication, context management, and workflow efficiency.

## 🎯 Purpose

The goal of MAIA is to help you quickly set up a new or existing project for more productive AI-assisted development by:

* Establishing a shared understanding and context via a structured "Memory Bank."
* Providing clear guidelines for interacting with your LLM assistant (`README-HUMAN.md`).
* Suggesting a system for defining project-specific coding rules that your LLM can follow.

## 🧩 Components Included

1. **`README-HUMAN.md`**: 
   * A comprehensive guide detailing best practices for human-LLM interaction, prompt engineering, leveraging an LLM agent's capabilities (like modes and tools), and managing the collaborative workflow.
   * **Action:** Read this first to get the most out of your LLM assistant!

2. **`memory-bank/` Directory**: 
   * A structured directory containing templates for key project context documents. These files are intended to be filled out at the beginning of a project and kept up-to-date to provide essential context to your LLM assistant.
   * Includes placeholders for:
       * `projectbrief.md`: High-level project goals and scope.
       * `productContext.md`: The "why" and "for whom" of the project.
       * `activeContext.md`: Current work focus, recent changes, next steps.
       * `systemPatterns.md`: System architecture, key technical decisions, design patterns.
       * `techContext.md`: Technologies used, development setup, technical constraints.
       * `progress.md`: What works, what's left, current status, known issues.

3. **`.cursor/rules/` Directory (Optional but Recommended)**:
   * A suggested location for defining project-specific coding conventions and patterns that your LLM assistant can learn and adhere to.
   * Includes:
       * `.gitkeep`: Ensures the directory is versioned even if initially empty.
       * `rules-init.mdc` (Generic Template): A sample rule that can be used to instruct an LLM agent (like Cursor) to analyze the current project's codebase and generate an initial set of coding rules.

4. **`.gitignore` (Basic)**:
   * A basic `.gitignore` file suitable for many Python projects or as a starting point.

## 🚀 How to Use This Framework

1. **Copy to Your Project:** Copy the relevant directories and files into the root of your new or existing software project.
   * You might want to rename the top-level directory to something like `.project_llm_guidance` or simply integrate its contents directly.
2. **Read `README-HUMAN.md`**: Familiarize yourself with the best practices for interacting with your LLM coding assistant.
3. **Initialize the `memory-bank/`**: 
   * Go through each Markdown file in the `memory-bank/` directory.
   * Fill in the placeholder information with details specific to your project.
   * Keep these documents (especially `activeContext.md` and `progress.md`) updated as your project evolves and your work focus changes.
4. **(Optional) Configure `.cursor/rules/`**:
   * If your LLM assistant supports a rules system (like Cursor), review the provided `rules-init.mdc`.
   * You can use it as a prompt to have your assistant analyze your codebase and generate initial rules.
   * Store these generated rules within this directory structure.
5. **Collaborate!** Start working with your LLM assistant, applying the principles from `README-HUMAN.md` and leveraging the context provided in the `memory-bank/`.

## 🙏 Contributing

This framework is a starting point. Feedback and suggestions for improvement are welcome! If you develop additional useful templates or refine the guidance, consider submitting a pull request or opening an issue.

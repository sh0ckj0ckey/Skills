---
name: personal-coding-style
description: Defines coding style guidance for practical engineering tasks. Focused on C#/.NET and XAML desktop applications including WPF, UWP, and WinUI 3, as well as Electron-based TypeScript client applications, especially those using Vue 3. Use when implementing features, extending existing code, following existing code style, making local code structure or layering decisions, migrating or porting functionality between files, modules, or languages, refactoring legacy or project code, reviewing existing code, or writing concise git commit messages. Do not use for technology selection, broad architecture design, or non-code writing tasks.
---

# Personal Coding Style

## Core Principles

- Prefer simple, direct, readable code.
- Keep changes focused on the requested task.
- Match the existing codebase style before introducing a new pattern.
- Prefer local changes over broad rewrites.
- Preserve existing behavior unless the task explicitly requires a behavior change.
- Avoid abstractions made only for possible future needs.
- Use explicit control flow and clear data flow instead of clever or overly generic code.
- Prefer modern language features when they improve readability, clarity, or conciseness.
- Aim for elegant code that is simple, cohesive, clearly structured, easy to understand, and naturally consistent with the surrounding codebase.
- Follow official conventions and broadly accepted best practices for the target stack.

## Judgment and Exceptions

- Treat these instructions as default preferences, not rigid rules.
- Keep open and divergent engineering judgment, and actively look for solutions that are simpler, clearer, more robust, or more elegant than the default preferences.
- If there is a solution that is clearly better than these default preferences, propose it, explain the reason, and explain why it fits the current codebase and task better.
- Do not add complexity only to appear clever or novel.
- If the current codebase, framework, runtime, performance requirements, safety, testability, concurrency, memory management, or platform constraints require a different approach, choose the better approach and explain why.
- If a design pattern, helper method, abstraction, state variable, compatibility layer, or broader change is genuinely useful for the current problem, propose it explicitly and explain the reason.
- Do not force simplicity when it would make the code less correct, less maintainable, harder to test, or inconsistent with the surrounding project.
- When there is a tradeoff, state it briefly and choose the option that best fits the current codebase and task.

## Codebase First

- Read nearby code before changing or adding code.
- Follow the existing naming, formatting, file organization, member ordering, error handling, async patterns, lifecycle patterns, and dependency usage.
- Prefer existing project helpers, services, components, commands, converters, stores, composables, utilities, and conventions over new ones.
- Do not introduce a new framework, library, design pattern, folder structure, or layering style unless explicitly requested or clearly required.
- When the existing codebase style conflicts with these preferences, follow the existing codebase style unless it is unsafe, clearly broken, or inappropriate for the requested change.

## Scope Control

- Do not modify unrelated code.
- Do not format unrelated files or unrelated sections of a file.
- If unrelated code has a bug, style issue, typo, or design problem, mention it in the response instead of changing it.
- Keep diffs small and reviewable.
- Avoid broad cleanup while implementing a narrow request.

## Feature Implementation

- Implement the requested behavior directly.
- Add only the files, types, methods, components, props, events, state, bindings, and dependencies needed for the current feature.
- Prefer clear conditionals, clear data flow, and direct composition.
- Prefer local state and local reasoning over shared or global state.
- Minimize temporary state variables when the logic can stay clear without them.
- Prefer passing values, closures, and functional composition over unnecessary mutable state.

## Existing-Code Extension

- When asked to build something similar to existing code, first identify the relevant existing implementation.
- Reuse the same structure, naming style, control flow, UI binding style, lifecycle handling, and error handling style where appropriate.
- If the existing pattern is unsafe or clearly flawed, point it out and propose a limited fix.

## Migration and Porting

- Preserve the existing behavior first.
- Map concepts from the source code to the target codebase style instead of copying structure mechanically.
- When porting between languages or UI stacks, prefer idiomatic target-side code while keeping the original behavior clear.
- The final code should look like natural code newly developed for the target project, not a mechanical copy of the old project.
- Do not add comments in the final code that mark a piece of code as corresponding to a specific old-project file, module, method, or location.
- Only describe old-to-new code mapping in the response or separate documentation when the user explicitly asks for migration mapping. Do not put it into production code.
- Keep names similar when it helps traceability, but adjust names when the target codebase has a clear convention.
- Do not introduce a compatibility layer unless it is required by the current migration.
- After migration, review both the migrated code and the surrounding module for behavior gaps, lifecycle issues, async issues, naming issues, and documentation issues.

## Refactoring

- Refactor to solve a concrete readability, duplication, correctness, maintainability, or consistency problem.
- Keep refactors small and reviewable.
- Do not split code into extra files only to make the structure look cleaner.
- Preserve behavior unless a behavior change is requested.
- Do not introduce factory patterns, manager classes, registries, generic wrappers, service layers, or other design patterns unless the current code clearly benefits from them.
- If a design pattern is appropriate, mention it explicitly and explain why it fits the current project size and problem.

## Local Structure Decisions

- Prefer inline logic when it remains readable.
- Avoid helper methods by default when the logic is only used once and is easier to understand inline.
- Use local functions when a small block deserves a name, needs to be reused locally, or would make the surrounding method easier to read without adding wider API surface.
- Introduce private helper methods only when they clearly improve readability, remove real duplication, match an existing project style, or reduce meaningful complexity.
- Avoid global state and long-lived mutable state unless it represents real application state.
- Prefer closures, parameters, return values, and immutable data flow where they keep the code clear.
- Avoid using version counters or similar state variables to handle async request freshness unless they are the simplest correct option.
- For async freshness, first consider whether closures, cancellation, request ownership, lifecycle-aware cleanup, or functional data flow can solve the problem more clearly.

## Encapsulation and Component Boundaries

- Prefer highly cohesive and loosely coupled local encapsulation.
- When implementing a user control, component, custom control, composable, service, or similar unit, give it clear internal responsibilities and clear external boundaries.
- Reusable UI controls should interact with the outside through parameters, properties, events, callbacks, commands, slots, emits, dependency properties, or explicit public APIs where possible.
- Avoid making reusable controls strongly depend on a specific external view model, store, page, window, parent component, or global state when a better boundary is available.
- A control or component may manage state that belongs to its own responsibility, but it should not own business state that belongs elsewhere.
- If a control only serves one specific page or business scenario, moderate coupling is acceptable. If it clearly has reuse value, prefer keeping it independent.
- When decoupling would significantly increase complexity, choose based on the current project size and real reuse needs, and explain the reason.

## C#/.NET and XAML Guidance

- Follow official C#/.NET naming, formatting, member ordering, async, event, disposal, and documentation conventions.
- Use modern C# syntax when it improves readability and remains appropriate for the project language version.
- In C#/.NET, use established idiomatic syntax such as `var`, target-typed `new`, and other common community conventions when they improve readability and match the project style.
- Prefer enabling and using modern .NET / C# features such as nullable reference types, implicit usings, file-scoped namespaces, global usings, and an appropriate latest language version, as long as they fit the target framework, project conventions, and existing code state.
- Do not enable new features in a way that causes broad unrelated changes, creates excessive warning noise, or breaks compatibility with existing code.
- For XAML desktop applications, follow the conventions of the current UI stack and project, including WPF, UWP, or WinUI 3 patterns.
- Keep view, view model, command, converter, service, and model responsibilities consistent with the existing project.
- Before making significant changes in a C# client project, check whether the project uses NativeAOT or ask the user when it cannot be determined.
- If the project uses NativeAOT, avoid approaches that are problematic for NativeAOT unless the project already handles them safely.
- Be careful with reflection, dynamic access, runtime code generation, serializers, dependency injection patterns, WinRT projection types, and APIs that may require trimming or AOT-specific configuration.
- When working with NativeAOT, trimming, WinRT projection types, serialization, or runtime metadata access, prefer approaches that can be statically analyzed, explicitly registered, or made compatible with the current trimming configuration.
- Use try-catch at the layer that can handle, translate, log, or recover from the error.
- Do not catch exceptions in lower layers only to hide them, return vague failure values, or duplicate logging.
- In layered modules, prefer letting errors propagate to an upper layer when that layer owns user-facing handling, logging, or recovery.

## Vue 3, TypeScript, and Electron Guidance

- Follow official Vue 3, TypeScript, and Electron conventions and best practices.
- In TypeScript, prefer explicit type annotations even when the IDE can infer simple types, and always declare return types for methods and functions.
- Follow the existing project style for Composition API, stores, composables, components, props, emits, lifecycle hooks, watchers, and IPC usage.
- Keep component state minimal and local when possible.
- Prefer computed values, derived data, closures, parameters, and explicit data flow over unnecessary mutable state.
- Clean up subscriptions, timers, event listeners, IPC handlers, and async work through lifecycle hooks when needed.
- Keep Electron main process, preload, renderer, and IPC responsibilities clear and consistent with the existing project.
- Avoid broad state management changes unless the current feature clearly needs them.
- For styles in Vue single-file components, prefer nested style rules where the nesting structure follows the parent-child structure in the template.
- Use style nesting to improve readability and express local structure. Do not create overly deep, heavy, or hard-to-override selectors only for nesting.
- Keep style scope clear, and prefer component-local styles, clear class names, and selector organization that matches the component structure.
- When designing Vue components in Electron applications, consider that the component may be used in multiple BrowserWindow instances.
- Do not assume by default that different BrowserWindow instances can directly share renderer memory, component state, store instances, or global variables.
- For components that may be reused across windows, prefer providing data and behavior through props, emits, slots, callbacks, explicit IPC APIs, or explicitly passed dependencies.
- Avoid making reusable components strongly depend on a window-level store, global singleton, parent-window state, or a specific BrowserWindow context unless the current project architecture clearly requires it.
- When data shared across windows needs a single source of truth, keep it in an upper layer such as the main process, persistent storage, IPC service, or an existing sync mechanism, instead of relying on local renderer state.
- A component may manage local state that belongs to its own UI and interaction responsibilities, but business data and cross-window shared data should be passed in or synchronized through explicit boundaries.

## Member and Code Ordering

- Follow the official or project-specific ordering conventions for fields, properties, constructors, methods, events, lifecycle hooks, computed values, watchers, handlers, and helper code.
- If the project has an established ordering style, follow it.
- Keep related code close together when that improves readability.
- Avoid moving unrelated members only for cosmetic ordering.

## Comments and Documentation

- Use simple, plain, easy-to-understand English.
- For public or important functions, methods, properties, classes, interfaces, and similar API surfaces, use complete documentation comments when appropriate.
- Use the documentation comment syntax of the target language or framework.
- In C#, use XML documentation comments such as `summary`, `param`, `returns`, `remarks`, `exception`, and other relevant tags.
- Fully document parameters, return values, remarks, constraints, side effects, and important behavior when they matter.
- Do not add decorative comments that only repeat the code.
- Prefer comments that explain why something exists, clarify non-obvious behavior, document constraints, or describe important edge cases.
- Check comment spelling, grammar, tag correctness, parameter names, return descriptions, and whether the comment still matches the code.

## Code Review

- Review carefully, rigorously, and comprehensively.
- Start from the larger module behavior, then inspect the newly written or changed code in detail.
- Prioritize correctness, behavior regressions, edge cases, maintainability risks, missing tests, memory leaks, race conditions, deadlocks, lifecycle issues, async cancellation, error handling, naming, spelling, and documentation accuracy.
- Point out over-engineering when it makes the code harder to understand or maintain.
- Focus on concrete issues in the current code.
- Avoid broad redesign suggestions unless the current design is causing a real problem.
- Keep review comments direct, specific, and actionable.

## Final Self-Review After Changes

- After writing, migrating, or refactoring code, review the changed code before responding.
- Check the surrounding module for integration issues, behavior mismatches, lifecycle problems, async risks, memory leaks, race conditions, deadlocks, naming issues, documentation issues, and style inconsistencies.
- Check that the implementation follows the existing project conventions.
- Check that no unrelated code was modified.
- Check that comments and documentation comments are accurate and use the correct syntax.
- Mention any remaining risks, assumptions, or unrelated issues found during the work.

## Git Commit Messages

- Use short, simple, plain English.
- Do not use Conventional Commits unless explicitly requested.
- Write clear and easy-to-understand sentences or sentence fragments.
- Describe what changed.
- Avoid vague messages like `Update code`, `Fix issue`, or `Refactor logic`.
- Avoid overly polished, formal, or convention-heavy wording.
- Prefer messages like:
  - `Fix login redirect`
  - `Update upload error handling`
  - `Move settings migration logic`
  - `Remove unused cache code`
  - `Handle empty project name`
  - `Keep window state after restart`

## Avoid

- Unnecessary helper methods.
- Unnecessary global or long-lived mutable state.
- Factory patterns without a clear construction problem.
- Manager classes, registries, generic wrappers, or service layers without a current need.
- Broad architecture changes for local tasks.
- Large rewrites for small requests.
- Speculative future-proofing.
- Version counters for async freshness when a clearer closure, cancellation, ownership, or lifecycle-based solution is available.
- Unrelated formatting or cleanup.
- Overly polished or convention-heavy commit messages.
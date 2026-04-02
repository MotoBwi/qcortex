---
name: android-gradle-dependency-bump
description: Workflow command scaffold for android-gradle-dependency-bump in qcortex.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /android-gradle-dependency-bump

Use this workflow when working on **android-gradle-dependency-bump** in `qcortex`.

## Goal

Bulk upgrade of Android/Kotlin/Gradle dependencies and related build files, typically via Dependabot or similar tools.

## Common Files

- `apps/android/app/build.gradle.kts`
- `apps/android/benchmark/build.gradle.kts`
- `apps/android/build.gradle.kts`
- `apps/android/gradle/wrapper/gradle-wrapper.jar`
- `apps/android/gradle/wrapper/gradle-wrapper.properties`
- `apps/android/gradlew`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Identify outdated dependencies in apps/android via automation.
- Update versions in build.gradle.kts, gradle-wrapper.properties, and related files.
- Update gradle-wrapper.jar and scripts if needed.
- Commit all changes together.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.
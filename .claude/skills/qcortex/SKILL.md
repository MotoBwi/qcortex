```markdown
# qcortex Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill covers the core development patterns, coding conventions, and automated workflows used in the `qcortex` repository. The project is primarily written in TypeScript, uses the Express framework for backend development, and follows a set of conventions for code style, commit messages, and testing. Automated workflows help maintain security, keep dependencies up-to-date, and ensure documentation accuracy.

## Coding Conventions

### File Naming
- **Style:** camelCase
- **Example:** `userController.ts`, `apiRoutes.ts`

### Import Style
- **Relative imports** are used throughout the codebase.
- **Example:**
  ```typescript
  import userService from '../services/userService'
  import { validateInput } from './utils/validateInput'
  ```

### Export Style
- **Mixed:** Both default and named exports are present.
- **Example:**
  ```typescript
  // Default export
  export default function handler(req, res) { ... }

  // Named export
  export function calculateScore(data: DataType): number { ... }
  ```

### Commit Patterns
- **Types:** Mixed (feature, fix, build, etc.)
- **Prefixes:** Commonly `fix`, `build`
- **Average length:** ~43 characters
- **Example:**
  ```
  fix: correct user validation logic
  build: update dependencies for security
  ```

## Workflows

### Security Dependency Upgrade
**Trigger:** When a security vulnerability is detected in a dependency  
**Command:** `/upgrade-dependency`

1. Detect vulnerability in a dependency (e.g., via Snyk or Dependabot).
2. Update the affected dependency version in `package.json` or equivalent manifest.
3. Commit the change with a message referencing the vulnerability or upgrade.
4. Optionally, merge an automated pull request.

**Files involved:**
- `package.json`
- `extensions/zalo/package.json`

**Example commit message:**
```
fix: upgrade lodash to address CVE-xxxx-xxxx
```

---

### Android Gradle Dependency Bump
**Trigger:** When dependencies in the Android project need to be updated (routine maintenance or new releases)  
**Command:** `/bump-android-deps`

1. Identify outdated dependencies in `apps/android` via automation.
2. Update versions in `build.gradle.kts`, `gradle-wrapper.properties`, and related files.
3. Update `gradle-wrapper.jar` and scripts if needed.
4. Commit all changes together.

**Files involved:**
- `apps/android/app/build.gradle.kts`
- `apps/android/benchmark/build.gradle.kts`
- `apps/android/build.gradle.kts`
- `apps/android/gradle/wrapper/gradle-wrapper.jar`
- `apps/android/gradle/wrapper/gradle-wrapper.properties`
- `apps/android/gradlew`
- `apps/android/gradlew.bat`

**Example commit message:**
```
build: bump Android dependencies to latest versions
```

---

### README Documentation Update
**Trigger:** When documentation needs to be clarified, updated, or corrected  
**Command:** `/update-readme`

1. Edit `README.md` with new or corrected information.
2. Commit the change with a message indicating a README update.

**Files involved:**
- `README.md`

**Example commit message:**
```
docs: update README with new setup instructions
```

## Testing Patterns

- **Framework:** [vitest](https://vitest.dev/)
- **Test file pattern:** Files end with `.test.ts`
- **Example:**
  ```typescript
  // userService.test.ts
  import { describe, it, expect } from 'vitest'
  import { getUserById } from './userService'

  describe('getUserById', () => {
    it('returns user for valid id', () => {
      expect(getUserById(1)).toEqual({ id: 1, name: 'Alice' })
    })
  })
  ```

## Commands

| Command              | Purpose                                                        |
|----------------------|----------------------------------------------------------------|
| /upgrade-dependency  | Upgrade dependencies to address security vulnerabilities       |
| /bump-android-deps   | Bulk upgrade Android/Kotlin/Gradle dependencies                |
| /update-readme       | Update the README.md documentation                            |
```
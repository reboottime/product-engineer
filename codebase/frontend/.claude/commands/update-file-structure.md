---
description: Update file structure documentation to reflect current codebase state
---

# Update File Structure Documentation

**Goal:** Update `docs/guidelines/reference.file-structure.md` to reflect the current codebase structure for improved LLM clarity and token efficiency.

## What to Document

### ✅ Include (Architecture-Level)

1. **Page Routes** - All pages in `app/` (routes visible to users)
2. **Server Actions** - All files in `app/actions/*` (API surface)
3. **Component Categories** - Top-level directories in `components/*`
4. **Key Utilities** - Important modules in `lib/*`
5. **Route Groups** - Organization patterns in `app/`

### ❌ Exclude (Too Granular)

- Individual sub-components within component categories
- Every utility function
- Internal implementation files (styles, configs)
- Test files

## Process

1. **Scan Current Structure**
   - List all pages: `app/**/page.tsx`
   - List Server Actions: `app/actions/*.ts`
   - List component categories: `components/*/`
   - List key utilities: `lib/*`

2. **Update Documentation**
   - Update directory tree in `docs/guidelines/reference.file-structure.md`
   - Add/update tables for:
     - Server Actions (API surface)
     - Component Categories
     - Key Utilities
   - Keep existing sections: Route Groups, Key Decisions, File Naming

3. **Abstraction Level**
   - Focus on "where would I find X?" questions
   - Document structure, not implementation
   - Keep it concise for token efficiency

## Expected Output

Updated `docs/guidelines/reference.file-structure.md` with:

- Current directory tree
- Complete list of page routes
- Complete list of Server Actions
- Component categories (not every component)
- Key utilities (not every function)

## When to Run

- After adding/removing pages
- After adding/removing Server Actions
- After major component reorganization
- Before creating PR for significant features
- When file structure documentation feels stale

---

**Now execute the update:**

1. Use Glob to scan the current structure
2. Read the current `docs/guidelines/reference.file-structure.md`
3. Update it with current state
4. Focus on architecture-level changes only

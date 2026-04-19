# Wiki Lint

Check wiki for issues and suggest improvements.

## When to Use

When user types `wiki:lint` or wants to check wiki quality.

## The Process

1. **Read all wiki pages**
   - List all .md files in workspace/knowledge-base/wiki/
   - Exclude INDEX.md and LOG.md
   - Read each page

2. **Check for orphan pages**
   - Pages with no incoming [[links]]
   - Search all wiki pages for links to each page

3. **Check for broken links**
   - Find all [[Page Name]] links
   - Verify target pages exist

4. **Check for contradictions**
   - Compare information across related pages
   - Flag potential conflicts

5. **Check for missing cross-links**
   - Identify pages that should link to each other
   - Suggest adding links

6. **Check for split/merge candidates**
   - Pages that are too long (>500 lines)
   - Pages that are too similar (should merge)

## Output

Report with:
- Orphan pages list
- Broken links list
- Contradictions found
- Missing cross-links suggestions
- Split/merge recommendations

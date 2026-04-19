# Wiki Ingest

Ingest sources from raw/ into wiki/.

## When to Use

When user types `wiki:ingest` or wants to process new sources from raw/ directory.

## The Process

1. **Find new sources**
   - List all .md files in workspace/knowledge-base/raw/articles/
   - List all .md files in workspace/knowledge-base/raw/docs/
   - Read workspace/knowledge-base/wiki/LOG.md to check which are already processed

2. **Read sources**
   - Read each new source file
   - Identify key concepts and topics

3. **Create wiki pages**
   - Create pages in workspace/knowledge-base/wiki/
   - Use Russian names with spaces (e.g., "Типы памяти LLM.md")
   - Condense information (wiki pages are shorter than sources)
   - Add cross-links using [[Page Name]] format

4. **Update INDEX.md**
   - Add new pages to appropriate sections
   - Keep sections: LLM, Obsidian, Интеграция, Claude Code
   - Update page count and date

5. **Update LOG.md**
   - Add new entry at the top with format: ## [YYYY-MM-DD] ingest | Description
   - List processed sources
   - List created/updated pages
   - Note cross-links added

6. **Commit**
   - git add workspace/knowledge-base/wiki/
   - git commit with descriptive message

## Output

Report:
- Number of sources processed
- Pages created/updated
- Cross-links added
- Commit hash

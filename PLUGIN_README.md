# Wiki Plugin

Knowledge base management plugin for Karpathy-style wiki.

## Commands

### wiki:ingest

Ingest sources from `raw/` into `wiki/`.

**Usage:**
```bash
wiki:ingest
```

**What it does:**
1. Scans `raw/articles/` and `raw/docs/` for markdown files
2. Reads all sources
3. Creates/updates wiki pages (Russian names with spaces)
4. Adds cross-links between related pages
5. Updates INDEX.md
6. Adds entry to LOG.md
7. Commits changes

**Example:**
```bash
# Add new article to raw/
cp article.md workspace/knowledge-base/raw/articles/

# Run ingest
wiki:ingest
```

### wiki:query

Query wiki pages and get synthesized answer.

**Usage:**
```bash
wiki:query <question>
```

**What it does:**
1. Reads INDEX.md to find relevant pages
2. Reads those pages
3. Synthesizes answer with citations
4. Optionally saves good answers as new wiki pages

**Example:**
```bash
wiki:query Как работает RAG в Obsidian?
wiki:query Какие плагины для LLM интеграции?
wiki:query Чем отличается superpowers от обычных skills?
```

### wiki:lint

Check wiki for issues and suggest improvements.

**Usage:**
```bash
wiki:lint
```

**What it checks:**
- Orphan pages (no incoming links)
- Contradictions between pages
- Outdated information
- Missing cross-links
- Broken wiki links
- Pages that should be split/merged

**Example:**
```bash
wiki:lint
```

## Installation

Plugin is already installed in `.claude/plugins/wiki/`.

Commands are available as:
- `wiki:ingest`
- `wiki:query`
- `wiki:lint`

## Structure

```
.claude/plugins/wiki/
├── plugin.json           # Plugin manifest
├── README.md            # This file
└── commands/
    ├── ingest.sh        # Ingest handler
    ├── query.sh         # Query handler
    └── lint.sh          # Lint handler
```

## How it works

Commands are bash scripts that signal Claude to perform the operation. Claude reads the signal and executes the appropriate workflow from CLAUDE.md.

## See also

- `workspace/knowledge-base/` - the actual wiki
- `CLAUDE.md` - wiki operations documentation
- `karpathy.md` - methodology reference

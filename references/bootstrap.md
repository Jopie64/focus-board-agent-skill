# Bootstrapping a Focus Board Repository

Create a new git repository (`main` branch) with this layout, matching the user's language for headings and starter text.

## Layout

- `journals/` — daily files (`YYYY-MM-DD.md`); seed with today's file.
- `pages/` — `Focus.md` (the five buckets, `type:: dashboard`), `contents.md` (sidebar shortcuts to `[[Focus]]` and key pages), and any initial work-item pages.
- `logseq/custom.css` — create an empty file upfront so Logseq does not generate an untracked file on first open.
- `logseq/config.edn` — configure ISO journal filenames, `:todo` workflow, default home page, and property-page exclusions so metadata keys do not clutter the graph:

```clojure
{
 :meta/version 1
 :preferred-workflow :todo
 :journal/file-name-format "yyyy-MM-dd"
 :journal/page-title-format "yyyy-MM-dd"
 :default-home {:page "Focus"}
 :property-pages/excludelist #{:why :url :ref :ref-url :type :waiting-on :agents :bucket}
}
```

- `.gitignore` — exclude Logseq local cache/backup folders:

```gitignore
logseq/bak/
logseq/.recycle/
logseq/version-files/
.DS_Store
Thumbs.db
```

## Notes

- Ask the user whether to push the new repository to a private remote (e.g., personal GitHub or company GitHub Enterprise), and record the local repo path in agent memory.

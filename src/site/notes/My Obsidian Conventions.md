---
{"dg-publish":true,"permalink":"/my-obsidian-conventions/","dg-note-properties":{}}
---

# Categories
## 🎨Theme used
### magicuser

## 🔌Plugins

### ☑️ Obsidian Configuration (`config.json`) – Pretty Formatted

```json
{
  "version": 4,
  "homepages": {
    "Main Homepage": {
      "value": "Home",
      "kind": "File",
      "openOnStartup": true,
      "openMode": "Keep open notes",
      "manualOpenMode": "Keep open notes",
      "view": "Default view",
      "revertView": true,
      "openWhenEmpty": false,
      "refreshDataview": false,
      "autoCreate": false,
      "autoScroll": false,
      "pin": false,
      "commands": [],
      "alwaysApply": false,
      "hideReleaseNotes": false
    }
  },
  "separateMobile": false,
  "_defaultViewMode": "default",
  "_livePreview": false,
  "_focusNewTab": "default",
  "_plugins": [
    "custom-sidebar-icons",
    "callout-toggles",
    "obsidian42-brat",
    "obsidian-auto-link-title",
    "obsidian-desmos",
    "editing-toolbar",
    "emoji-shortcodes",
    "obsidian-emoji-toolbar",
    "epub-importer",
    "obsidian-excalidraw-plugin",
    "flowershow",
    "folder-notes",
    "frontmatter-markdown-links",
    "homepage",
    "image-converter",
    "obsidian-latex-suite",
    "link-preview",
    "obsidian-list-callouts",
    "metadata-menu",
    "obsidian-mind-map",
    "multi-properties",
    "optimize-canvas-connections",
    "obsidian-plantuml",
    "obsidian-plotly",
    "quickadd",
    "recent-files-obsidian",
    "solve",
    "obsidian-style-settings",
    "templater-obsidian",
    "obsidian-textgenerator-plugin",
    "univer",
    "waypoint",
    "ytranscript",
    "execute-code",
    "obsidian-meta-bind-plugin",
    "table-editor-obsidian",
    "notebook-navigator",
    "featured-image",
    "obsidian-icon-folder",
    "obsidian-book-search-plugin",
    "obsidian-markmind",
    "obsidian-hover-editor",
    "litegallery",
    "radial-timeline",
    "inbox-organiser",
    "various-complements",
    "obsidian-map-view",
    "iconic",
    "chronology",
    "emoji-magic",
    "buttons",
    "dataview-serializer",
    "dataview",
    "code-language-completer",
    "extended-graph",
    "juliaplots",
    "obsidian-tagfolder",
    "obsidian-quiet-outline",
    "soundscapes"
  ],
  "_internalPlugins": [
    "file-explorer",
    "global-search",
    "switcher",
    "graph",
    "backlink",
    "canvas",
    "outgoing-link",
    "tag-pane",
    "properties",
    "page-preview",
    "daily-notes",
    "templates",
    "note-composer",
    "command-palette",
    "editor-status",
    "bookmarks",
    "outline",
    "word-count",
    "workspaces",
    "file-recovery",
    "bases"
  ],
  "_obsidianVersion": "1.9.14"
}
```

---
dg-publish: true

#### Summary

| Section | Details |
|-------|--------|
| **Obsidian Version** | `1.9.14` |
| **Homepage** | `Home.md` opens on startup |
| **Total Plugins** | **59** community plugins |
| **Core Plugins** | **21** enabled |
| **Live Preview** | Disabled (`false`) |
| **Mobile Sync** | Same config (`separateMobile: false`) |

---

#### Notable Plugins

##### Productivity & Navigation
- `homepage`, `quickadd`, `templater-obsidian`
- `recent-files-obsidian`, `notebook-navigator`
- `waypoint`, `radial-timeline`

##### Visual & Creative
- `obsidian-excalidraw-plugin`, `obsidian-mind-map`
- `obsidian-plotly`, `juliaplots`, `obsidian-desmos`
- `obsidian-plantuml`, `litegallery`

##### Data & Tables
- `dataview`, `dataview-serializer`
- `table-editor-obsidian`, `multi-properties`
- `metadata-menu`, `obsidian-meta-bind-plugin`

##### Media & Import
- `epub-importer`, `obsidian-book-search-plugin`
- `ytranscript`, `soundscapes`

##### UI & UX
- `obsidian-style-settings`, `iconic`, `obsidian-icon-folder`
- `editing-toolbar`, `obsidian-latex-suite`
- `buttons`, `emoji-magic`

---

#### How to Use This

1. **Backup** your current `.obsidian/config.json`
2. **Paste** this pretty version back if needed
3. Use it to **compare** with other setups
4. Share with **friends or forums** for help

---

**Want a downloadable `.json` file?**  
Just copy the code above → paste into a file → save as `config-pretty.json`

Let me know if you want:
- A **plugin category breakdown**
- **Missing recommended plugins**
- **Performance optimization tips** for 59 plugins
- Export as **Markdown table** or **HTML**

## Notes
1) Folder names: 🅰️ **T**itle Case / **P**roper Case

### Latex
1) Important Formulas in latex are enclosed in a white box using `\bbox[white, 3pt, border: 1px solid black]`
$$
\large\bbox[white, 3pt, border: 1px solid black]{\vec{a} \cdot \vec{b} = ||\vec{a}|| \cdot ||\vec{b}|| \cos{\theta}}
$$

and some more impotant formulas under the main formulas will have color `lightgray` as seen below and any note/impotant information regarding the theory/formula will be in `[!ub-blue]` (untitled callout) which could be a `[!multi-column]` callout if there are multiple notes clubbed together as seen below under a header `#### Note`

##### Note: [Multi Column Callout \| Modular CSS Layout](https://efemkay.github.io/obsidian-modular-css-layout/multi-column/02-multi-column-callout/)
> [!multi-column]
> 
> > [!ub-blue]
> > 1. **Collinear Vectors**: If **$\large{\vec{a}}$** and **$\large{\vec{b}}$** point in the same direction (**$\large{\theta = 0^\circ}$**), **$\large{\cos{0} = 1}$**, maximizing the dot product:
> >    $$
> >    \large\bbox[lightgray, 3pt, border: 1px solid black]{\vec{a} \cdot \vec{b} = ||\vec{a}|| \cdot ||\vec{b}||}
> >    $$
> >    The projection of **$\large{\vec{a}}$** onto **$\large{\vec{b}}$** is **$\large{\vec{a}}$** itself.
>
> > [!ub-blue]
> > 2. **Perpendicular Vectors**: If **$\large{\vec{a}}$** and **$\large{\vec{b}}$** are orthogonal (**$\large{\theta = 90^\circ}$**), **$\large{\cos{90} = 0}$**, so:
> >    $$
> >    \large\bbox[lightgray, 3pt, border: 1px solid black]{\vec{a} \cdot \vec{b} = 0}
> >    $$
> >    No part of **$\large{\vec{a}}$** aligns with **$\large{\vec{b}}$**, so the dot product is zero.
> 
> > [!ub-blue]
> > 3. **General Case**: For any angle, the dot product quantifies the **extent of alignment** between the vectors.


## Pop Up info message.
- **Royalty**: Degree of nobility<i class="muc"><span>Nobility refers to ==a privileged class of people — often receiving hereditary titles== — also called the aristocracy. You know the type. They hang around manors and castles, or curry favor at court.</span></i>
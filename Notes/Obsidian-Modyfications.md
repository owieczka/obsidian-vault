---
date: 2022-08-07
---
# Modyfikacje Obsydiana

W obsydianie można kliknąć shift+ctrl+I

## Cusstom Snipped
Plik `obsydian.css` w folderze `snippets`

### Zmiana odległości numerów lini od krawędzi
```css
body.plugin-sliding-panes-rotate-header .workspace > .mod-root > .workspace-leaf > .workspace-leaf-content > .view-content .markdown-source-view.mod-cm6 .cm-scroller,
.markdown-source-view.mod-cm6 .cm-scroller {
  /*font-family: var(--font-text);*/
  padding: 10px;
}
```

### Zmiana odległości tytułu stony od góry
```css
/*Top padding of the card*/
.cm-scroller {
    padding-top: 15px !important;
}
```

## Daily Notes

Ustawić format daty na `YYYY/MM-MMMM/YYYY-MM-DD` aby daily były tworzone w pod folderach z datami

Trzeba używać `templater` który ma więcej opcji tworzenia wzorców. 
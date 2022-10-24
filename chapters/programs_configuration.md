# Programs configuration

`WARNING`: Development-related programs are not listed here. But VSCode I am using for make the manuals.  

## My programs list
1. Brave browser.
2. Telegram.
3. Visual Studio Code.
4. mpv as media player.
5. 7zip file manager.
6. Discord.
7. Lightshot.

## Brave browser
1. `Extensions`:
- AdGuard.
- Better History.
- Todoist.
- Mate Translate.
- HTTPS Everywhere.
- Void Theme - Black and Minimal.
2. `Settings`:
- Setup specified pages when brave open. 
- Change the standard font.
- Disable `WebTorrent` and `Widivine`.

## Visual Studio Code
1. `Extensions`:
- Material Icon Theme.
- Russian Language Pack for Visual Studio Code.
- Winter is Coming Theme.
2. VS Code configuration:
```json
// Workbench
"workbench.editor.limit.value": 5,
"workbench.editor.showTabs": false,
"workbench.statusBar.visible": false,
"workbench.editor.showIcons": false,
"workbench.startupEditor": "none",
"workbench.iconTheme": "material-icon-theme",
"workbench.colorTheme": "The Digital Life",
// Workbench

// Explorer
"explorer.confirmDelete": false,
"explorer.confirmDragAndDrop": false,
// Explorer

// Editor
"editor.bracketPairColorization.enabled": true,
"editor.guides.indentation": false,
"editor.renderLineHighlight": "none",
"editor.lineNumbers": "interval",
"editor.minimap.enabled": false,
"editor.overviewRulerBorder": false,
"editor.acceptSuggestionOnEnter": "off",
"editor.codeActionsOnSave": {
    "source.fixAll": true
},
"editor.foldingImportsByDefault": true,
"editor.inlineSuggest.enabled": true,
"editor.linkedEditing": true,
"editor.quickSuggestions": {
    "other": "off",
    "comments": "off",
    "strings": "off"
},
"editor.scrollBeyondLastColumn": 0,
"editor.unicodeHighlight.nonBasicASCII": false,
"editor.suggestSelection": "recentlyUsedByPrefix",
"editor.unicodeHighlight.ambiguousCharacters": false,
"editor.formatOnSave": true,
"editor.scrollbar.horizontal": "hidden",
"editor.scrollbar.vertical": "hidden",
"editor.tokenColorCustomizations": {
    "textMateRules": [
        {
            "scope": [
                "comment",
                "entity.name.type.class",
                "keyword",
                "constant",
                "storage.modifier",
                "storage.type.class.js"
            ],
            "settings": {
                "fontStyle": "italic"
            }
        },
        {
            "scope": [
                "invalid",
                "keyword.operator",
                "constant.numeric.css",
                "keyword.other.unit.px.css",
                "constant.numeric.decimal.js",
                "constant.numeric.json"
            ],
            "settings": {
                "fontStyle": ""
            }
        }
    ]
},
// Editor

// Font
"editor.fontSize": 18,
"editor.fontLigatures": "'ss01', 'ss02', 'ss03', 'ss04', 'ss05', 'ss06', 'zero', 'onum'",
"editor.fontFamily": "JetbrainsMono NF",
"editor.fontWeight": "350",
// Font

// Files
"files.autoSave": "off",
"files.defaultLanguage": "markdown",
// Files

// Terminal
"terminal.external.windowsExec": "wt.exe",
"terminal.integrated.fontSize": 18,
// Terminal

// Window
"window.menuBarVisibility": "toggle",
"window.zoomLevel": 1,
// Window

// Other
"breadcrumbs.enabled": false,
"security.workspace.trust.untrustedFiles": "open",
// Other
```

## Telegram
1. `Settings`:
- Turn on the `Dark Theme`.
- Set the background chat's picture.

## Discord
1. `Download and install` [`BetterDiscord`](https://betterdiscord.app/).
2. `Download and install the plugins`:
- Translator.
- ImageUtilities.
- GameActivityToggle.
- Freemoji.
- ReadAllNotifications.
- CallTimeCounter.

## Next...
Chapter 3: [`Development Setup`](./dev_setup.md).
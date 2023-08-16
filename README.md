Automatically format document on save. Current release includes:

- FormatDocument: Same as Edit > Advance > Format Document
- RemoveAndSort: Same as Edit > IntelliSense > Remove and Sort Usings
- SmartRemoveAndSort: Apply remove and sort to .cs without #if.
- UnifyLineBreak: Enforce line break to CRLF or LF.
- UnifyEndOfFile: Enforce only one line break at the end of file.
- TabToSpace: Convert tab to space.
- ForceUtf8: Force file encoding to UTF8 with BOM,and support no Bom
- RemoveTrailingSpaces: Remove trailing spaces. It is mostly for Visual Studio 2012 and below, which won't remove trailing spaces when formatting.

<image src="img/utf-8_no_bom.png">

And more:

- AutoSaveOnDeactivated: save files when Visual Studio deactivated.
- File extension filters.
- Batch formatting in solution explorer.
- Settings in Tools -> Options -> Format on Save.

I found it convenient to unify source code format throughout the develop team. If you have any suggestion, feel free to tell me.

For different Visual Studio versions:

- [For VS2015-2019](https://marketplace.visualstudio.com/items?itemName=WinstonFeng.FormatonSave)
- [For VS2022](https://marketplace.visualstudio.com/items?itemName=WinstonFeng.VSFormatOnSave2022)

## Updates

### 3.2

- When formatting in project/solution, with a `.editorconfig` set to space, FormatDocument use tab instead. It seems FormatDocument ignore .editorconfig, and only apply VS's settings. So I recall the old trick: run TabToSpace after FormatDocument.
- Optimize hints for menu item to reduce misunderstandings.
- Fix when "Extension cause delayed FormatDocument" filter is empty, all files are processed.

### v3.1

- Fix undo may fail in .cshtml files.
- Fix invalid more information links.
- Remove deprecated options.
- Change default line break style to Windows.

### v3.0

- New feature AutoSaveOnDeactivated, save files when Visual Studio deactivated.
- Fix naming inconsistency. #15
- In VS2022, .razor and .cshtml file will delayed Edit.FormatDocument command, which modify document after saving. I managed to capture the modification and save again. #14, #16

### v2.2

- Add individual filter for every feature.
- Force CRLF for .aspx files, or Visual Studio formatting will produce weird empty lines.
- UnifyEndOfFile is disabled by default.
- Remove VS2017 tab to space bug fix, since the bug has gone in the latest version.
- Add support for SpecFlow .feature files. #12
- Show "Enable/Disable format on save" on menu item to avoid misleading.
- Upload VS2022 version to the marketplace. Removed the GitHub version.

### v2.1

- Supports Visual Studio 2022 Preview. Please download Visual Studio 2022 version from GitHub.
- Add Enable/Disable button to Tools menu.
- RemoveAndSort, UnifyLineBreak, TabToSpace, ForceUtf8WithBom are disabled by default.
- Skip binary files.
- Optimize option page messages.
- Remove deprecated RemoveTrailingSpaces.

### v2.0

- Upgrade to AsyncPackage. Only supports Visual Studio 2015 and above.
- Can format multiple items in solution view.

### v1.12

- Reactivate current editing document after saving all.

### v1.11

- Add SmartRemoveAndSort: Apply remove and sort to .cs without #if.
- Add RemoveTrailingSpaces: Remove trailing spaces. It is mostly for Visual Studio 2012, which won't remove trailing spaces when formatting.

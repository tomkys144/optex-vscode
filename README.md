# OpTeX for VSCode 

This extension provides support in VSCode for **OpTeX**. A LuaTeX format based on Plain TeX macros and on OPmac macros. Look at [**OpTeX** project webpage](https://petr.olsak.net/optex/) for more info. 

This extension aims to make writing OpTeX documents and packages as least as comfortable as writing LaTeX ones, if not better.

## Quick start

If you are writing an OpTeX package with `.opm` extension, then that may be recognized automatically.

If not, or you write simple `.tex` file, you will probably need to specify to vscode you are using OpTeX language.

Either type ` > Change Language Mode` into command palette and then select `optex` or click the language selection in lower right corned. `Ctrl-K m ` shortcut should also open the selection menu 
on default keybindings. 

## Features

This extension currently provides:

- Syntax Highlighting
- Snippets

### Syntax Highlighting

\!\[feature X\]\(images/feature-x.png\)

Syntax highlighting is implemented with a custom TextMate grammar file. Meaning the grammar should be in theory easily adaptable for other editors. 
(In practice though, working with TextMate Grammar is terrible.)

I have written my grammar from scratch to be as clear and concise as possible. Sometimes the highlighting might seem blunt and inconsistent. Please do not hesitate to leave feedback 
and report **issues** in the [**github repository**](https://github.com/BasileosFelices/optex-vscode).

TeX Math highlighting is directly imported from [vscode's own](https://github.com/jlelong/vscode-latex-basics/blob/main/syntaxes/TeX.tmLanguage.json) grammar for TeX, which is published under MIT license.
OpTeX does not make many changes to TeX default math.

Apart from fixing the basic TeX highlighting to include all macros from OpTeX (which might start with and include `_`), many more features are also implemented:

- OpTeX documentation **comments support**
    - Includes highlighting for special documentation creation macros 
- Important and often used keywords highlighting
- "Complex" **macro declaration** recognition (or as complex as I managed)

**⚠️ Note**: This extension only provides scopes for syntax highlighting. Actual colors depend purely on your VSCode theme. Please keep in mind not all themes distinguish 
between the scopes used here. For example, in many themes, internal OpTeX macros appear the same as all other macros.   

### Snippets

There are currently 7 smart snippets that could help accelerate your work. The most used blocks are defined:

- Item list `\begitems`
- Verbatim text `\begtt`
- Text block `\begblock`
- Multi-column `\begmulti`
- Documentation block `\_doc`
- BibTeX file import `\usebib`
- Quick document setup `\setupdocument`

All snippets use vscode options for jumping your cursor to the parameters for customization.

### YAML

For easier and usable editing, both the grammar and snippets are written in yaml. Before usage, these files must be converted to json. I used npm js-yaml module, as recommended by 
[vscode guide](https://code.visualstudio.com/api/language-extensions/syntax-highlight-guide). 

## Release Notes

Releases are being documented in the [changelog](CHANGELOG.md).

## What's missing

- Intellisense autocomplete
- Hover documentation
- Smarter semantic highlighting
- Automatic build/compilation 
- Bugfixes for syntax highlighting probably

Please **leave an issue** for any feature requests that you would utilize and find yourself missing! Write even if they are written above as that both tells me what to focus on and 
gives me motivation to implement these features at all.

## License

[MIT open-source license](LICENSE)

## Used resources

* [Visual Studio Code's Language extension Guide](https://code.visualstudio.com/api/language-extensions/syntax-highlight-guide)
* [Writing a TextMate Grammar: Some Lessons Learned](https://www.apeth.com/nonblog/stories/textmatebundle.html)

**Enjoy!**

# CSS syntax highlighting in VS Code

Adds syntax highlighting to CSS files in VS Code

Derived from https://github.com/atom/language-css.
Originally [converted](http://flight-manual.atom.io/hacking-atom/sections/converting-from-textmate)
from the [CSS TextMate bundle](https://github.com/textmate/css.tmbundle).

Contributions are greatly appreciated. Please fork this repository and open a
pull request to add snippets, make grammar tweaks, etc.

## Error recovery

Recovery after malformed input must preserve valid and forward-compatible CSS.
Brace recovery is limited to `layer()` in `@import` and functional selector
arguments where an unescaped `{` cannot be legal outside a string or comment.
Shared value functions and general-enclosed conditions allow balanced blocks,
including nested blocks and blocks that span lines. An unclosed media condition
may therefore keep the rest of the file in its header scope.

When changing recovery, test valid strings, escapes, comments and balanced
blocks, along with the scopes after malformed input. Recovery helps while
editing; it does not mean a browser accepts the input.

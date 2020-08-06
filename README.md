# node-toy-cli

REFER to https://stackoverflow.com/questions/10585683/how-do-you-edit-existing-text-and-move-the-cursor-around-in-the-terminal/10830168

- Position the Cursor: \033[<L>;<C>H or \033[<L>;<C>f (puts the cursor at line L and column C)
- Move the cursor up N lines: \033[<N>A
- Move the cursor down N lines: \033[<N>B
- Move the cursor forward N columns: \033[<N>C
- Move the cursor backward N columns: \033[<N>D
- Clear the screen, move to (0,0): \033[2J
- Erase to end of line: \033[K
- Save cursor position: \033[s
- Restore cursor position: \033[u
  The latter two codes(Save cursor position and Restore cursor position) are NOT honoured by many terminal emulators. The only ones that I'm aware of that do are xterm and nxterm - even though the majority of terminal emulators are based on xterm code.
  Can't be used in template strings or strict mode, but you can replace the octal `\033` with hex `\x1b` or unicode `\u001b`

[ANSI Escape sequences - VT100/VT52](http://ascii-table.com/ansi-escape-sequences-vt-100.php)

Extra point about closure

T-Combinator

```javascript
let y = (g) => ((f) => f(f))((self) => g((...args) => self(self)(...args)));
let f = y((self) => (n) => (n < 0 ? 0 : n + self(n - 1)));
console.log(f(100));
```

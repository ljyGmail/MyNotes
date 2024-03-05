# Chapter 1 The Vim Way

## Tip 1. Meet the Dot Command

- The dot command can be used repeat `x`, `dd`, `>` Normal commands, but it can also be used with Insert mode.

- The Dot Command Is a Micro Macro

## Tip 2. Don't Repeat Yourself

- One keystroke to move, another to execute.

- Two for the Price of One

`C -> c$`  
`s -> cl`  
`S -> ^C`  
`I -> ^i`  
`A -> $a`  
`o -> A<CR>`  
`O -> ko`

## Tip 3. Take One Step Back, Then Three Forward

- Pad each + sign with spaces

```javascript
var foo = "method(" + argument1 + "," + arguments2 + ")";
```

```vim
f+
s + <Esc>
;
.
;.
;.
```

- Make the Motion Repeatable

## Tip 4. Act, Repeat, Reverse

| Intent                           | Act                   | Repeat | Reverse |
| -------------------------------- | --------------------- | ------ | ------- |
| Make a change                    | {edit}                | `.`    | `U`     |
| Scan line for next character     | `f{char}`/`t{char}`   | `;`    | `,`     |
| Scan line for previous character | `F{char}`/`T{char}`   | `;`    | `,`     |
| Scan document for next match     | /pattern`<CR>`        | `n`    | `N`     |
| Scan document for previous match | ?pattern`<CR>`        | `n`    | `N`     |
| Perform substitution             | :s/target/replacement | `&`    | `u`     |
| Execute a sequence of changes    | `qx{change}q`         | `@x`   | `u`     |

## Tip 5. Find and Replace by Hand

* Use `*` to executes a search for the word under the cursor at the moment.

* Make the Change Repeatable
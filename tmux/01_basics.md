# Chapter 1 Learning the Basics

## Check version

```bash
tmux -V
```

## Starting tmux

```bash
tmux
```

## Exit

```bash
exit
```

## Creating Named Sessions

```bash
tmux new-session -s basic

* Short version:
tmux new -s basic
```

## The Command Prefix

```bash
Ctrl-b
```

### Clock

```bash
Prefix + t
```

## Detaching and Attaching Sessions

```bash
Prefix + d
```

### Reattaching to Existing Sessions

```bash
tmux list-sessions

* Short version
tmux ls
```

- If only one session is running, use the following command to attach to the session.

```bash
tmux attach
```

- Create a new session in the background:

```bash
tmux new -s second_session -d
```

- Attach to a session by specify the session name:

```bash
tmux attach -t second_session
```

### Killing Sessions

```bash
tmux kill-session -t basic
tmux kill-session -t second_session
```

## Working with Windows

- Create a session and specify the name of the first window:

```bash
tmux new -s windows -n shell
```

### Creating and Naming Windows

```bash
Prefix + c
```

- Rename a window

```bash
Prefix + ,
```

### Moving Between Windows

```bash
Prefix + n
Prefix + p

Prefix 0
Prefix 1
...
```

- Display a visual menu of windows

```bash
Prefix + w
```

- Find a window by name:

```bash
Prefix + f
```

- Close a window:

```bash
Prefix + &
```

## Working with Panes

- Split window vertically

```bash
Prefix + %
```

- Split window horizontally

```bash
Prefix + "
```

- Cycle through the panes

```bash
Prefix + o

Prefix + Up/Down/Left/Right
```

## Pane Layouts

- Cycle through layouts

```bash
Prefix + SpaceBar
```

### Closing Panes

```Bash
Prefix + x
```

## Working with Command Mode

- Enter command mode:

```bash
Prefix + :
```

- Create a new window

```bash
new-window -n console
```

- Create a new window and start the top program:

```bash
new-window -n console processes "top"
```

- Help:

```bash
Prefix + ?
```

# qcd (Quickly Change Directory)

Copy the following script into a configuration file and source it.

```bash
# Define the qcd function
qcd () {
    # Accept 1 argument that's a string key, and perform a differe
    # "cd" operation for each key
    case "$1" in
        work)
            cd $HOME/Workspace/
            ;;
        shell)
            cd $HOME/Workspace/ShellScriptWorkspace/shell_script_s
            ;;
        *)
            # The supplied argument was not one of the supported k
            echo "qcd: unknown key '$1'"
            return 1
            ;;
    esac
    # Helpfully print the current directory name in dicate where y
    pwd
}

# Set up tab completion
complete -W "work shell" qcd
```

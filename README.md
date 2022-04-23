# Pathasaurus
Pathasaurus is a PATH manager for POSIX systems. It basically just stores a registry of paths which you can easily add or remove from the command line, and then use that to build a path string that you can use to populate your path variable.

## Installing Pathasaurus
Just take the `psrs` script in this repo and put it wherever. Then put the following in your `.bashrc`, `.bash_profile`, `.zshrc` or whatever your startup script of choice is:
```
export PATHASAURUS=`path/to/psrs build`
export PATH=${PATHASAURUS}:$PATH
```
And restart your terminal.
## Usage
### Commands
`psrs list`
Lists all currently registered paths.

`psrs add [path] [label]`
Registers a path to the path registry. If `path` is not specified, it defaults to the current working directory if not specified. If `label` is not specified, it defaults to the last path component of the path.

`psrs rm <label>`
Removes the path with the specified label from the registry.

`psrs build`
Prints a colon separated list of the paths in the registry, for use as part of the PATH environment variable.
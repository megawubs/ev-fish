# ev-fish

`envdir` for fish shell

Load environment variables from directories and files.

## Usage

By default, `ev` looks for environment variable directories in `~/.config/env`,
set `EVPATH` to change this. `EVPATH` can be a list of directories.

```
Usage:
 ev DIR           # Load all environment variables from DIR
 ev FILE          # Load a single environment variable from a FILE
 ev -u DIR        # Unload all environment variables from DIR
 ev (-h | --help) # Show this message
```

### Example

```
$ env | grep FOO
$ env | grep BAR
$ tree ~/.config/env/foo/
/home/joe/.config/env/foo/
├── FOO
└── BAR

0 directories, 2 files
$ ev foo
FOO
BAR
$ env | grep FOO
FOO=foo123
$ env | grep VAULT_AUTH
BAR=bar
```


## Installation

### Using [fundle](https://github.com/tuvistavie/fundle) (recommended)

Add

```
fundle plugin 'joehillen/ev-fish'
```

to your `config.fish` and run `fundle install`.

### Manually

Put `functions/ev.fish` in `~/.config/fish/functions/` directory,
and put `completions/ev.fish` in `~/.config/fish/completions/`.

or run `make`

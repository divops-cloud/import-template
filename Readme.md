# [import](https://import.pw)

`import` is a simple and fast module system for Bash and other Unix shells.

Inspired by Go's import command, you specify the URL of the shell script,
and the `import` function downloads the file and caches it to `~/.import-cache`,
_forever_.

The code will never change from below your feet, and will continute to work
offline.


## 👋 Example

[git.io/fAWiz][gist] ← This URL contains a simple `add` shell function:

```bash
add() {
  expr "$1" + "$2"
}
```

You can use the `import` function to download, cache, and use that function in
your own script:

```bash
#!/usr/bin/env import

# The URL is downloaded once, cached forever, and then sourced
import git.io/fAWiz

add 20 22
# 42
```


## ⚙️ Compatibility

The core `import` function is fully POSIX-compliant, and maximum compatability
is the goal. `import` is unit tested against the following shell implementations:

 * [ash](https://en.wikipedia.org/wiki/Almquist_shell) - Almquist Shell (BusyBox `ash` and Debian `dash`)
 * [ksh](https://en.wikipedia.org/wiki/KornShell) - KornShell (`oksh`, `mksh` and `loksh` flavors)
 * [zsh](https://en.wikipedia.org/wiki/Z_shell) - Z Shell
 * [bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)) - GNU's Bourne Again SHell


## 📚 Documentation

 * [Authentication](./docs/authentication.md) - Making private GitHub repos work
 * [Caching](./docs/caching.md) - Explanation of the caching strategy
 * [Configuration](./docs/config.md) - Customizing `import` with env vars
 * [Implicit Imports](./docs/implicit-imports.md) - Importing "core" modules
 * [Installation](./docs/install.md) - Installing and bootstrapping `import`
 * [Relative Imports](./docs/relative-imports.md) - Implementation for relative imports

[gist]: https://git.io/fAWiz

---
title: Commands Reference
---


## Commands, Commands, Commands

Welcome to the pluto command line tool.
To see all commands type:

    $ pluto help


resulting in:

```
NAME
    pluto - another planet generator - lets you build web pages from published web feeds

SYNOPSIS
    pluto [global options] command [command options] [arguments...]

GLOBAL OPTIONS
    -c, --config=PATH - Configuration Path (default: ~/.pluto)
    -q, --quiet       - Only show warnings, errors and fatal messages
    --verbose         - (Debug) Show debug messages
    --version         - Display the program version
    --help            - Show this message

COMMANDS
    build, b      - Build planet
    install, i    - Install template pack
    list, ls, l   - List installed template packs
    update, up, u - Update planet feeds
    merge, m      - Merge planet template pack
    about, a      - (Debug) Show more version info
    help          - Shows a list of commands or help for one command
```


## `build` Command    {#build}

```
NAME
    build - Build planet

SYNOPSIS
    pluto [global options] build [command options] FILE

COMMAND OPTIONS
    -o, --output=PATH       - Output Path (default: .)
    -t, --template=MANIFEST - Template Manifest (default: blank)
    -d, --dbpath=PATH       - Database path (default: .)
    -n, --dbname=NAME       - Database name (default: <PLANET>.db e.g. ruby.db)

EXAMPLE
    pluto build ruby.yml
    pluto build ruby.yml --template news
    pluto b ruby
    pluto b ruby -t news
    pluto b            # will use pluto.ini|pluto.yml|planet.ini|planet.yml if present
```


## `list` Command    {#list}

```
NAME
    list - List installed template packs

SYNOPSIS
    pluto [global options] list

EXAMPLE
   pluto list
   pluto ls
```


## `install` Command    {#install}

```
NAME
    install - Install template pack

SYNOPSIS
    pluto [global options] install MANIFEST

EXAMPLE
   pluto install news      # install "river of news" template pack
```


## `update` Command     {#update}

```
NAME
    update - Update planet feeds

COMMAND OPTIONS
    -d, --dbpath=PATH       - Database path (default: .)
    -n, --dbname=NAME       - Database name (default: <PLANET>.db e.g. ruby.db)

SYNOPSIS
    pluto [global options] update FILE

EXAMPLE
    pluto update ruby.yml
    pluto u ruby
```


## `merge` Command      {#merge}

```
NAME
    merge - Merge planet template pack

SYNOPSIS
    pluto [global options] merge [command options] FILE

COMMAND OPTIONS
    -o, --output=PATH       - Output Path (default: .)
    -t, --template=MANIFEST - Template Manifest (default: blank)
    -d, --dbpath=PATH       - Database path (default: .)
    -n, --dbname=NAME       - Database name (default: <PLANET>.db e.g. ruby.db)

EXAMPLE
    pluto merge ruby.yml
    pluto merge ruby.yml --template news
    pluto m ruby
    pluto m ruby -t news
```

# MkDocs knep

## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.


## Flera projekt samtidigt

För att köra flera MkDocs-sidor parallellt.

```bash
mkdocs serve -a 127.0.0.1:8001
```

> Startar servern på port 8001 istället för standard 8000.
> Öppna i ny terminalflik/fönster så kan du ha t.ex. både projektet och lathunden igång samtidigt.

---
For full documentation visit [mkdocs.org](https://www.mkdocs.org).
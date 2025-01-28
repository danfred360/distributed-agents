# IDE

clone the repo and open it with [vscode](https://code.visualstudio.com/).

```sh
git clone git@github.com:danfred360/distributed-agents.git

code distrubuted-agents
```

## model provider

install [ollama](./local-setup/ollama.md) and run the models.

```sh
# pull embedding model
ollama pull nomic-embed-text

# code completion and chat
ollama pull deepseek-coder-v2-16b

# if you want to use r1 for chat
ollama run deepseek-r1-8b

# serve the models
ollama serve
```

## ai assistant

install the recommended extensions from `.vscode/extensions.json` and install dependencies with `yarn install`.

copy the config file from [the continue doc](./local-setup/continue.md) into `~/.continue/config.json`.

reload your vscode window to load the recommended extensions with `cmd+shift+p` and type "Reload Window".

open continue with `cmd+l` to open chat (select text first to add it to context). tab completion is available by typing a few characters in the code editory. use the `@` symbol for context providers like `@Continue` or add docs sites to your `~/.continue/config.json` file to index them and provide context with `@Docs`.



[continue](https://github.com/continuedev/continue) is an opensource code assistant that connects large language models and context providers to autocomplete and chat in vscode (and jetbrains).

you can use the following `~/.continue/config.json` file to configure the docs provider, chat, and code completion:

> note: generate a github access token [here](https://github.com/settings/personal-access-tokens) and paste it into the `docs.params.githubToken` object in the config so that the docs provider doesn't get rate limited by github.

```json
{
  "models": [
    {
      "title": "Deepseek Coder v2 16B",
      "provider": "ollama",
      "model": "deepseek-coder-v2:16b"
    }
  ],
  "tabAutocompleteModel": {
    "title": "Deepseek Coder v2 16B",
    "provider": "ollama",
    "model": "deepseek-coder-v2:16b"
  },
  "embeddingsProvider": {
    "provider": "ollama",
    "model": "nomic-embed-text"
  },
  "contextProviders": [
    {
      "name": "code",
      "params": {}
    },
    {
      "name": "docs",
      "params": {
        "githubToken": "" // 60 requests per hour without token
      }
    },
    {
      "name": "diff",
      "params": {}
    },
    {
      "name": "terminal",
      "params": {}
    },
    {
      "name": "problems",
      "params": {}
    },
    {
      "name": "folder",
      "params": {}
    },
    {
      "name": "codebase",
      "params": {}
    }
  ],
  "slashCommands": [
    {
      "name": "share",
      "description": "Export the current chat session to markdown"
    },
    {
      "name": "cmd",
      "description": "Generate a shell command"
    },
    {
      "name": "commit",
      "description": "Generate a git commit message"
    }
  ],
  "experimental": {
    "useChromiumForDocsCrawling": false
  },
  "docs": [
    {
      "title": "private wiki",
      "startUrl": "http://localhost:8300/docs",
      "faviconUrl": "http://localhost:8300/docsassets/favicon.ico",
      "useLocalCrawling": true
    }
  ]
}
```
# configuração do BiomeJS

## Instalação

```
npm install --save-dev --save-exact @biomejs/biome && npx @biomejs/biome init
```



## Configuração VSCODE

```
mkdir .vscode && touch .vscode/settings.json && echo '{
  "window.zoomLevel": 0,
  "editor.inlineSuggest.enabled": true,
  "editor.codeActionsOnSave": {
    "// source.fixAll.eslint": "explicit",
    "quickfix.biome": "explicit",
    "source.organizeImports.biome": "explicit"
  },
  "editor.defaultFormatter": "biomejs.biome",
  "search.showLineNumbers": false,
  "workbench.editor.enablePreview": false,
  "workbench.list.openMode": "doubleClick",
  "git.ignoreLimitWarning": true,
  "[prisma]": {
    "editor.formatOnSave": true,
    "editor.defaultFormatter": "Prisma.prisma"
  }
}' > .vscode/settings.json
```

## Extensão
```
touch .vscode/extensions.json && echo '{
  "recommendations": [
    "biomejs.biome"
  ]
}' > .vscode/extensions.json
```

## Arquivo de configuração do BiomeJS
Aqui você vai copiar o valor abaixo e colar no arquivo biome.json do seu projeto

```
{
  "$schema": "https://biomejs.dev/schemas/1.9.4/schema.json",
  "vcs": {
    "enabled": false,
    "clientKind": "git",
    "useIgnoreFile": false
  },
  "files": {
    "ignoreUnknown": false,
    "ignore": []
  },
  "formatter": {
    "enabled": true,
    "indentStyle": "space",
    "indentWidth": 2,
    "lineWidth": 120,
    "useEditorconfig": true,
    "lineEnding": "lf",
    "attributePosition": "auto"
  },
  "javascript": {
    "formatter": {
      "arrowParentheses": "asNeeded",
      "bracketSameLine": false,
      "bracketSpacing": true,
      "jsxQuoteStyle": "double",
      "quoteStyle": "single",
      "quoteProperties": "asNeeded",
      "semicolons": "asNeeded",
      "trailingCommas": "all"
    }
  },
  "organizeImports": {
    "enabled": true
  },
  "linter": {
    "enabled": true,
    "rules": {
      "recommended": true,
      "suspicious": {
        "noConsole": "error"
      },
      "correctness": {
        "noEmptyPattern": {
          "level": "warn"
        },
"noUnusedImports": {
          "level": "error",
          "fix": "safe"
        },
        "noUnusedVariables": {
          "level": "warn",
          "fix": "safe"
        }
      }
    }
  }
}
```

## Scripts do Biome

```
"lint": "npx @biomejs/biome lint --write .",
"format": "npx @biomejs/biome format --write .",
"lint:fix": "npx @biomejs/biome check --write ."
```


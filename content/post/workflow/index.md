---
title: "Mon Workflow en markdown"
description: Voici mon environnement de travail pour optimiser ma prise de note.
date: 2023-11-09T22:56:48Z
image: cover.png
slug: vscode-workflow
hidden: false
comments: false
draft: false
categories:
  - Markdown
---

## Introduction

Le **markdown** est un langage de balisage créé en 2004, il a pour but d'être une syntaxe facile à lire et à écrire. Personnellement je l'utilise pour écrire mes cours, prendre des notes ou bien même pour faire les pages de mon portfolio.

---

## Éditeur de texte

Comme éditeur de texte autant pour de la programmation, que pour de la prise de notes, j'utilise [VSCodium](https://vscodium.com/). C'est une alternative à VSCode de **Microsoft** sauf que tous les trackers sont supprimés et le code source est disponible. Il est même possible de configurer VSCodium pour qu'il accède à la marketplace des extensions de Visual Studio Code. Pour ceci, il suffit d'ajouter les 4 lignes ci-dessous dans le fichier `/usr/share/codium/resources/app/product.json`.

```json
    "extensionsGallery": {
    "serviceUrl": "https://marketplace.visualstudio.com/_apis/public/gallery",
    "cacheUrl": "https://vscode.blob.core.windows.net/gallery/index",
    "itemUrl": "https://marketplace.visualstudio.com/items"
    },
```

### Mes extensions

Pour ce qui est des extensions j'en utilise 3 qui me permettent de gagner du temps, d'avoir un fichier markdown très lisible et organisé.

#### Markdown All In One

- [Doc](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)
- Ajouter des shortcuts dans VSCodium (mettre en gras, mettre en italique)
- Créer et mettre à jour le sommaire
- Redimensionner les tableaux

#### Markdown Lint

- [Doc](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)
- Afficher les erreurs de syntaxes

#### Markdown Preview Enhanced

- [Doc](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced)
- Afficher une preview du fichier markdown (ctrl k + ctrl v)
- Insérer un tableaux dans le fichier

### Fichier de configuration

Afin de configurer des actions et des paramètres dans son workflow, il est possible d'ajouter un fichier `.vscode/settings.json` dans votre workdir. Ici, ce code en json me permet de formater mon fichier avec l'extensions markdown all in one à chaque fois que je sauvegarde. De nombreux autres paramètres sont disponibles, tout dépend du besoin de chacun.

```json
{
  "[markdown]": {
    "editor.defaultFormatter": "yzhang.markdown-all-in-one"
  },
  "editor.formatOnSave": true
}
```

## Conclusion

Tout ce workflow est donc très utile dans ma rédaction au quotidien, par exemple pour régider cette article ainsi que tout le reste de mon site ! Et me permet donc d'avoir des notes très lisible dans n'importe quel environnement.

Le markdown est également le format utilisé dans la documentation de projet (github, gitlab), mais aussi souvent dans les wikis (bookstack, mkdocs).

---
title: "ZWiki"
description: Création d'un wiki personnel afin d'y mettre tout type d'information.
date: 2024-10-06T22:56:48Z
image: cover.png
slug: wiki
hidden: false
comments: false
draft: true
categories:
  - Wiki
---

## Introduction

Avec le nombre d'informations qui arrive vers moi chaque jour dans de nombreux domaines, des centaines de pages de notes manuscrites éparpillées un peu partout et jamais réutilisé, et toujours le souci de régler un problème pour la 20e fois sans se souvenir de la solution comme les 19 fois précédentes. 😆

Il me manquait donc un outil pour me servir de **second cerveau** 🧠 afin d'avoir toutes ces pages de notes ou ces erreurs déjà résolues **rassemblées** au même endroit.

L'expression du **besoin** était donc présente avec des conditions obligatoires qui se sont dessinées au fil des différents tests :

- Rapidité d'accessibilité
- Rédaction des pages en Markdown
- Outil léger
- Hébergement local

## Qu'est ce que MkDocs ?

> MkDocs est un générateur de site statique rapide et simple, destiné à la création de documentation. Les fichiers de la documentation sont écrits en Markdown et configurés à l'aide d'un seul fichier de configuration YAML.

Cette définition présente sur le site de [MkDocs](https://www.mkdocs.org/) m'a directement inspiré une fois que je suis tombé dessus, car ceci répondait à mes 4 besoins exprimés ci-dessus, et j'ai donc décidé de me lancer dans le test
de cet outil.

![Site MkDocs](mkdocs.png)

La première version de mon **wiki** utilisait cet outil. J'ai utilisé un **Dockerfile** afin de pouvoir conteneuriser l'outil et de pouvoir l'utiliser en local sans besoin d'installer le paquet python **mkdocs**.

Seul bémol de cet outil est qu'il pique un peu les yeux. C'est ceci qui m'a motivé à trouver un thème !

### Material

Material est un framework qui s'utilise par-dessus **MkDocs** et va ainsi permettre de générer un site statique personnalisable via une multitude d'options, mais également la possibilité d'ajouté des plugins.

Ceci va permettre d'avoir un rendu très propre tout en minimisant la partie configuration, car bon nombre de fonctionnalités qui sont déjà intégrées dans le framework et une simple ligne dans le fichier de configuration permet de les ajouter.

![Exemple MkDocs avec Material](mkdocs_example.png)

## Mise en place du wiki

Pour mettre en place cet outil, je me suis basé sur la [documentation](https://squidfunk.github.io/mkdocs-material/creating-your-site/) de **Material** en suivant la mise en place via **docker**.

Une fois le projet initialisé, on se retrouve avec l'arborescence suivante :

```bash
.
├── Dockerfile
├── docs
│   ├── assets
│   ├── Finances
│   ├── index.md
│   ├── Livres
│   └── Tech
├── mkdocs.yaml
└── README.md
```

- **Dockerfile** : Permet la construction de l'image donc avec les paquets python nécessaires
- **docs** : Représente l'arborescence de notre wiki
- **mkdocs.yaml** : Fichier de configuration du wiki

### Configuration


## Déploiement

## Conclusion

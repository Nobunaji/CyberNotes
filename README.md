# CyberNotes

Ce dépôt contient une collection de notes, fiches et solutions de challenges liées à la cybersécurité, au réseau, à l'OSINT et à l'exploitation Web.

Il sert de base de connaissances personnelle pour centraliser des rappels de commandes, des outils, des méthodes de reconnaissance et des écritures de résolution de défis.

## Objectif

- Regrouper les notes de formation et de recherche.
- Garder une trace des commandes, concepts et outils utiles.
- Documenter les défis et exercices résolus.
- Avoir un référentiel rapide de consultation pour les sujets de sécurité informatique.

## Structure du projet

<pre>
CyberNotes/
├── Bash/
│   ├── <a href="./Bash/base.md">base.md</a>
│   └── <a href="./Bash/utilitaire_reseau.md">utilitaire_reseau.md</a>
├── OSINT/
│   └── <a href="./OSINT/nmap.md">nmap.md</a>
├── Root-Me Challenges/
│   ├── App - Script/
│   │   ├── <a href="./Root-Me%20Challenges/App%20-%20Script/Challenge_01.md">Challenge_01.md</a>
│   │   ├── <a href="./Root-Me%20Challenges/App%20-%20Script/Challenge_02.md">Challenge_02.md</a>
│   │   ├── <a href="./Root-Me%20Challenges/App%20-%20Script/Challenge_03.md">Challenge_03.md</a>
│   │   ├── <a href="./Root-Me%20Challenges/App%20-%20Script/Challenge_04.md">Challenge_04.md</a>
│   │   ├── <a href="./Root-Me%20Challenges/App%20-%20Script/Challenge_05.md">Challenge_05.md</a>
│   │   └── <a href="./Root-Me%20Challenges/App%20-%20Script/Challenge_06.md">Challenge_06.md</a>
│   └── Web - Server/
│       ├── #1 - Very Easy/
│       │   ├── <a href="./Root-Me%20Challenges/Web%20-%20Server/%231%20-%20Very%20Easy/Challenge_01.md">Challenge_01.md</a>
│       │   ├── <a href="./Root-Me%20Challenges/Web%20-%20Server/%231%20-%20Very%20Easy/Challenge_02.md">Challenge_02.md</a>
│       │   ├── <a href="./Root-Me%20Challenges/Web%20-%20Server/%231%20-%20Very%20Easy/Challenge_03.md">Challenge_03.md</a>
│       │   ├── <a href="./Root-Me%20Challenges/Web%20-%20Server/%231%20-%20Very%20Easy/Challenge_04.md">Challenge_04.md</a>
│       │   ├── <a href="./Root-Me%20Challenges/Web%20-%20Server/%231%20-%20Very%20Easy/Challenge_05.md">Challenge_05.md</a>
│       │   └── <a href="./Root-Me%20Challenges/Web%20-%20Server/%231%20-%20Very%20Easy/Challenge_06.md">Challenge_06.md</a>
│       └── #2 - Easy/
│           └── <a href="./Root-Me%20Challenges/Web%20-%20Server/%232%20-%20Easy/Challenge_07.md">Challenge_07.md</a>
└── <a href="./README.md">README.md</a>
</pre>

## Contenus principaux

### Bash

Fiches sur les commandes shell, la redirection des flux, les filtres (`grep`, `sed`, `cut`, `tr`, etc.) et les utilitaires réseau.

### OSINT

Méthodes et outils de collecte d'informations, notamment sur l'usage et les options de `nmap`.

### Root-Me Challenges

Notes et solutions de défis de différents niveaux, classés par catégorie. Chaque fichier inclut le sujet du challenge dans son titre pour faciliter la recherche rapide :

- App - Script : Bash, Sudo, PowerShell, AppArmor
- Web - Server : HTML, HTTP, PHP, API, authentification faible

## Index des challenges

### App - Script

- [Challenge_01.md](./Root-Me%20Challenges/App%20-%20Script/Challenge_01.md) — Bash — Système 1
- [Challenge_02.md](./Root-Me%20Challenges/App%20-%20Script/Challenge_02.md) — Sudo — Faiblesse de configuration
- [Challenge_03.md](./Root-Me%20Challenges/App%20-%20Script/Challenge_03.md) — Bash — Système 2
- [Challenge_04.md](./Root-Me%20Challenges/App%20-%20Script/Challenge_04.md) — À compléter
- [Challenge_05.md](./Root-Me%20Challenges/App%20-%20Script/Challenge_05.md) — PowerShell — Command Injection
- [Challenge_06.md](./Root-Me%20Challenges/App%20-%20Script/Challenge_06.md) — AppArmor — Jail Introduction

### Web - Server

#### Niveau 1 : Très facile

- [Challenge_01.md](./Root-Me%20Challenges/Web%20-%20Server/%231%20-%20Very%20Easy/Challenge_01.md) — HTML - Code Source
- [Challenge_02.md](./Root-Me%20Challenges/Web%20-%20Server/%231%20-%20Very%20Easy/Challenge_02.md) — HTTP - Contournement de filtrage IP
- [Challenge_03.md](./Root-Me%20Challenges/Web%20-%20Server/%231%20-%20Very%20Easy/Challenge_03.md) — HTTP - Open Redirect
- [Challenge_04.md](./Root-Me%20Challenges/Web%20-%20Server/%231%20-%20Very%20Easy/Challenge_04.md) — HTTP - User Agent
- [Challenge_05.md](./Root-Me%20Challenges/Web%20-%20Server/%231%20-%20Very%20Easy/Challenge_05.md) — Weak Password
- [Challenge_06.md](./Root-Me%20Challenges/Web%20-%20Server/%231%20-%20Very%20Easy/Challenge_06.md) — PHP - Injection de Commande

#### Niveau 2 : Facile

- [Challenge_07.md](./Root-Me%20Challenges/Web%20-%20Server/%232%20-%20Easy/Challenge_07.md) — API - Broken Access

## Remarque

Ce dépôt est avant tout un carnet de notes personnel de travail et d'apprentissage. Il peut être enrichi ou modifié au fil des exercices et des découvertes.

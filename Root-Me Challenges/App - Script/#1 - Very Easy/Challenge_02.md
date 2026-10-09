# Exercice 2 — Sudo — Faiblesse de configuration

## Description

Ce challenge illustre une mauvaise configuration de `sudo` permettant à un utilisateur d'exécuter une commande avec des privilèges trop élevés sans authentification ou avec une restriction insuffisante.

## Principe

Une règle `sudoers` trop permissive peut permettre à un utilisateur d'exécuter une commande critique comme :

```bash
sudo /usr/bin/passwd
```

ou une commande plus dangereuse, selon la configuration.

## Analyse

La vérification se fait souvent via :

```bash
sudo -l
```

et la lecture du fichier de configuration :

```bash
sudo visudo
```

## Exemple de mauvaise configuration

```sudoers
user ALL=(ALL) NOPASSWD: /usr/bin/ls
```

## Explication

Si un utilisateur peut exécuter des commandes en `sudo` sans mot de passe, il peut parfois escalader ses privilèges au-delà de ce qu'il devrait pouvoir faire. L'objectif est de repérer et d'exploiter cette faiblesse.

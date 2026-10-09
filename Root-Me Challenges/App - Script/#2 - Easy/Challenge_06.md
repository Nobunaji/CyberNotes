# Exercice 6 — AppArmor — Jail Introduction

## Description

Ce challenge a pour objectif de comprendre les mécanismes de confinement système via AppArmor.

## Objectif

Identifier le comportement imposé par le profil AppArmor et comprendre comment une application est limitée dans ses accès au système de fichiers et aux ressources.

## Analyse

AppArmor applique un profil de sécurité à un binaire ou un programme. Le profil décrit précisément les fichiers et permissions autorisés.

## Exemple de profil

```text
/usr/bin/example {
  /etc/passwd r,
  /tmp/* rw,
  deny /etc/shadow r,
}
```

## Explication

Le but d’AppArmor est de limiter les capacités d’un processus, même s’il est compromis. L’exécution d’une commande hors des chemins autorisés se retrouve bloquée par le profil.

## À retenir

- AppArmor repose sur des profils restrictifs.
- Les accès non autorisés sont refusés.
- Une bonne compréhension du profil permet d’anticiper ce qu’un programme peut faire.

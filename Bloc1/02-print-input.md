# 02 — Ton premier programme : `print` et `input`

**Ce que tu vas apprendre :** faire afficher un message à ton programme, et lui faire poser une question.

Tout au long du bloc, tu vas construire **ta carte d'identité** : un programme qui te pose des questions et te répond. Il va grandir à chaque guide.

---

## Afficher un message avec `print`

Dans l'éditeur de Thonny, ouvre ton fichier `carte.py` (ou crée-le, voir le [guide 01](01-installation-thonny.md#enregistre-ton-travail)) et écris :

```python
print("Bonjour!")
```

Clique sur ▶ (ou `F5`). Dans la console, tu vois :

```
Bonjour!
```

Bravo, c'est ton premier programme.

- `print` veut dire « affiche ».
- Ce qu'on veut afficher va **entre parenthèses**.
- Le texte va **entre guillemets** `"…"`. En programmation, un texte s'appelle une **chaîne de caractères** (*string* en anglais).

Un programme s'exécute **de haut en bas**, une ligne à la fois :

```python
print("Bonjour!")
print("Bienvenue au club de programmation.")
```

> [!tip] Les erreurs, c'est normal
> Enlève un guillemet et relance : Thonny affiche un message en rouge. Ce n'est pas grave, c'est même utile. Lis la dernière ligne du message : elle dit souvent ce qui ne va pas, et sur quelle ligne. Remets le guillemet, et ça repart.

### Exercice 1

Fais afficher trois lignes : ton prénom, ton niveau scolaire et ton jeu ou ton film préféré.

## Poser une question avec `input`

`input` affiche une question, **attend** que l'utilisateur tape une réponse, puis donne cette réponse au programme.

```python
nom = input("Comment t'appelles-tu? ")
print("Salut", nom)
```

Lance le programme. Il attend : clique dans la console, tape ton prénom et appuie sur **Entrée**.

```
Comment t'appelles-tu? Léa
Salut Léa
```

- `nom = …` garde la réponse dans une **variable** appelée `nom`. Tu vas tout savoir sur les variables au [guide 03](03-variables-types.md).
- Dans `print`, on peut mettre plusieurs choses séparées par des virgules. Python met une espace entre chacune.
- Laisse une espace à la fin de la question (`"…? "`), sinon la réponse est collée au point d'interrogation.

### Exercice 2 — Ta carte d'identité, version 1

Dans `carte.py`, écris un programme qui :

1. demande le prénom ;
2. demande la ville où tu habites ;
3. affiche une phrase qui utilise les deux réponses.

```
Comment t'appelles-tu? Léa
Où habites-tu? Sherbrooke
Salut Léa, de Sherbrooke!
```

> [!tip] Indice
> Tu as besoin de deux `input`, chacun gardé dans sa propre variable. Pour coller le `!` sans espace, tu peux écrire `print("Salut " + nom + ", de " + ville + "!")`. Le `+` colle des textes ensemble.

## Défi bonus

Fais afficher un petit dessin avec plusieurs `print`, comme un chat, une fusée ou les initiales de ton nom en gros caractères :

```
 /\_/\
( o.o )
 > ^ <
```

Ensuite, ajoute un `input` qui demande le nom de l'animal et l'affiche sous le dessin.

---

Suite : [03 — Variables et types](03-variables-types.md)

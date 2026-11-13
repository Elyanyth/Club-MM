# 07 — Les listes

**Ce que tu vas apprendre :** ranger plusieurs valeurs dans une seule variable, puis les parcourir avec une boucle.

Jusqu'ici, une variable contenait **une** valeur. Pour garder tes 5 jeux préférés, il faudrait 5 variables : `jeu1`, `jeu2`, `jeu3`… Pas pratique. Une **liste** les range toutes ensemble.

---

## Créer une liste

```python
jeux = ["Minecraft", "Mario Kart", "Zelda"]
print(jeux)
```

- Une liste s'écrit entre **crochets** `[ ]`.
- Les éléments sont séparés par des **virgules**.
- Une liste peut contenir n'importe quel type : `notes = [80, 90, 70]`, et même rien du tout : `vide = []`.

Lance le programme, puis regarde le panneau **Variables** : `jeux` contient toute la liste.

## Accéder à un élément : l'indice

Chaque élément a une position, qu'on appelle son **indice**. **On commence à compter à 0.**

```python
jeux = ["Minecraft", "Mario Kart", "Zelda"]
print(jeux[0])    # Minecraft
print(jeux[2])    # Zelda
print(jeux[-1])   # Zelda : -1 veut dire « le dernier »
```

| Indice | `0` | `1` | `2` |
|---|---|---|---|
| Élément | `"Minecraft"` | `"Mario Kart"` | `"Zelda"` |

On peut aussi **remplacer** un élément :

```python
jeux[1] = "Fortnite"
```

> [!important] `IndexError`
> `jeux[3]` provoque une erreur `IndexError: list index out of range` : la liste a 3 éléments, donc le dernier indice est `2`. C'est l'erreur la plus courante avec les listes. Rappelle-toi : on compte à partir de 0, comme `range`.

## Modifier une liste

| Écriture | Ce qu'elle fait |
|---|---|
| `jeux.append("Tetris")` | ajoute `"Tetris"` **à la fin** |
| `jeux.insert(0, "Tetris")` | ajoute `"Tetris"` à l'indice `0` (au début) |
| `jeux.remove("Zelda")` | enlève le premier `"Zelda"` trouvé |
| `jeux.pop()` | enlève le dernier élément (et le donne) |
| `len(jeux)` | donne le nombre d'éléments |
| `"Zelda" in jeux` | `True` si `"Zelda"` est dans la liste |
| `sorted(jeux)` | donne une copie triée de la liste |

Le `in` est très pratique dans un `if` :

```python
if "Zelda" in jeux:
    print("Bon choix!")
```

## Parcourir une liste avec `for`

Tu connais déjà `for lettre in "Python"`. Ça marche pareil avec une liste : à chaque tour, la variable prend l'élément suivant.

```python
jeux = ["Minecraft", "Mario Kart", "Zelda"]
for jeu in jeux:
    print(f"J'aime {jeu}")
```

```
J'aime Minecraft
J'aime Mario Kart
J'aime Zelda
```

C'est **la** façon la plus courante d'utiliser une liste.

## Remplir une liste avec une boucle

On part souvent d'une liste vide et on ajoute les éléments un à un :

```python
notes = []
for i in range(3):
    note = int(input("Une note : "))
    notes.append(note)
print(notes)
```

---

### Exercice 1 — Regarde la liste grandir

Lance le dernier exemple (les notes) dans le debugger (`Ctrl+F5`). Avance avec `F6` et observe `notes` dans le panneau **Variables** : `[]`, puis `[80]`, puis `[80, 90]`… Avant chaque `append`, **devine** à quoi ressemblera la liste.

### Exercice 2 — Ta carte d'identité, version 5

Ajoute à `carte.py` :

1. une liste `loisirs`, vide au départ ;
2. une boucle qui demande 3 loisirs et les ajoute à la liste ;
3. l'affichage de chaque loisir sur sa propre ligne, précédé d'un tiret.

```
Nomme un loisir : soccer
Nomme un loisir : dessin
Nomme un loisir : jeux vidéo
Tes loisirs :
- soccer
- dessin
- jeux vidéo
```

### Exercice 3 — La moyenne, pour de vrai

Avec une liste de notes (`notes = [80, 90, 70, 65, 100]`), calcule et affiche :

1. la moyenne ;
2. la note la plus haute, **sans** utiliser `max`.

<details>
<summary>💡 Indice (clique pour afficher)</summary>

Imagine que tu lis les notes une à une sur une feuille, sans pouvoir revenir en arrière. Qu'est-ce que tu dois retenir dans ta tête pour connaître la plus haute à la fin ?

</details>

Change les notes de la liste : ton programme doit marcher sans autre modification.

### Exercice 4 — La liste d'épicerie

Écris un programme qui demande des articles un à un, **jusqu'à** ce que l'utilisateur tape `fin`. Si l'article est déjà dans la liste, affiche « Déjà dans la liste! » au lieu de l'ajouter. À la fin, affiche le nombre d'articles et la liste triée.

<details>
<summary>💡 Indice (clique pour afficher)</summary>

Sais-tu à l'avance combien d'articles l'utilisateur va entrer ? Relis [`while` ou `for` ?](06-boucles.md#while-ou-for-) au guide 06. Pour savoir si un article est déjà là, cherche dans le tableau de [Modifier une liste](#modifier-une-liste).

</details>

## Défi bonus

1. **À l'envers :** affiche les éléments d'une liste du dernier au premier, sans utiliser `reverse` ni `sorted`.

   <details>
   <summary>💡 Indice (clique pour afficher)</summary>

   Quels sont le premier et le dernier indice de la liste ? Tu veux les parcourir dans l'autre sens. Le tableau de [`for` et `range`](06-boucles.md#for-et-range--répéter-un-nombre-de-fois-précis) du guide 06 montre comment compter à reculons, et rappelle-toi où `range` s'arrête.

   </details>

2. **Le compteur :** dans `lancers = [3, 6, 1, 6, 2, 6, 4]`, compte combien de fois le `6` apparaît, avec une boucle.
3. **Le piège de la copie :** devine ce qu'affiche ce programme, puis lance-le dans le debugger.
   ```python
   a = [1, 2, 3]
   b = a
   b.append(4)
   print(a)
   ```
   Surprise ? `b = a` ne copie pas la liste : `a` et `b` sont deux étiquettes sur **la même** liste. Pour une vraie copie, écris `b = a.copy()`.

## Pour aller plus loin : les compréhensions de listes

Python a un raccourci pour créer une liste à partir d'une autre :

```python
nombres = [1, 2, 3, 4, 5]
carres = [n * n for n in nombres]           # [1, 4, 9, 16, 25]
pairs = [n for n in nombres if n % 2 == 0]   # [2, 4]
```

C'est exactement une boucle `for` avec un `append`, écrite sur une ligne. Essaie de réécrire `carres` avec une boucle normale pour t'en convaincre.

---

Suite : [08 — Les dictionnaires](08-dictionnaires.md)

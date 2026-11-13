# 06 — Les boucles

**Ce que tu vas apprendre :** faire répéter des instructions à ton programme avec `while` et `for`.

---

## `while` : répéter tant que…

```python
compte = 1
while compte <= 5:
    print(compte)
    compte = compte + 1
print("Fini!")
```

`while` ressemble à `if`, mais au lieu de s'exécuter une fois, le bloc **recommence** tant que la condition est vraie. Ici : on affiche `compte`, on l'augmente de 1, on revient à la condition… jusqu'à ce que `compte` vaille 6.

> [!important] La boucle infinie
> Si la condition ne devient jamais fausse, la boucle ne s'arrête jamais. Enlève la ligne `compte = compte + 1` et lance le programme : il affiche `1` sans fin. Clique sur ■ (**Stop**) pour l'arrêter. Dans une boucle `while`, vérifie toujours que quelque chose **change** à chaque tour.

### Répéter une question jusqu'à une bonne réponse

C'est l'usage le plus courant de `while` :

```python
mot_de_passe = input("Mot de passe : ")
while mot_de_passe != "python123":
    print("Mauvais mot de passe.")
    mot_de_passe = input("Mot de passe : ")
print("Accès autorisé!")
```

## `for` et `range` : répéter un nombre de fois précis

```python
for i in range(5):
    print("Bonjour!")
```

Ce programme affiche « Bonjour! » 5 fois. À chaque tour, la variable `i` prend la valeur suivante de `range(5)` : `0`, `1`, `2`, `3`, `4`.

| Écriture | Valeurs données | Remarque |
|---|---|---|
| `range(5)` | 0, 1, 2, 3, 4 | commence à 0, **s'arrête avant** 5 |
| `range(1, 6)` | 1, 2, 3, 4, 5 | de 1 jusqu'à 6 **non compris** |
| `range(0, 10, 2)` | 0, 2, 4, 6, 8 | de 2 en 2 |
| `range(10, 0, -1)` | 10, 9, 8, …, 1 | à reculons |

On peut aussi parcourir un texte, lettre par lettre :

```python
for lettre in "Python":
    print(lettre)
```

## `while` ou `for` ?

- Tu sais **combien de fois** répéter ? → `for`.
- Tu répètes **jusqu'à ce que** quelque chose arrive (une bonne réponse, un score atteint…) ? → `while`.

---

### Exercice 1 — Regarde la boucle tourner

Lance le premier exemple (`compte` de 1 à 5) dans le debugger (`Ctrl+F5`). Avance avec `F6` et observe :

- la flèche qui **remonte** au `while` à chaque tour ;
- la valeur de `compte` dans le panneau Variables ;
- le moment exact où la condition devient fausse (utilise `F7` sur la ligne du `while`).

### Exercice 2 — Le compte à rebours

Avec une boucle `for`, affiche `10, 9, 8, …, 1`, puis `Décollage! 🚀`.

### Exercice 3 — Ta carte d'identité, version 4

Ajoute à `carte.py` :

1. une vérification de l'âge : tant que la personne entre un âge plus petit que 0 ou plus grand que 120, redemande-le ;
2. à la fin, affiche le prénom autant de fois que la personne a de lettres dans son prénom. Pour connaître le nombre de caractères d'un texte, utilise `len` : `len("Léa")` donne `3`.

### Exercice 4 — La table de multiplication

Demande un nombre et affiche sa table de multiplication de 1 à 10 :

```
7 x 1 = 7
7 x 2 = 14
...
7 x 10 = 70
```

### Exercice 5 — La somme

Demande un nombre `n` et calcule la somme de tous les nombres de 1 à `n`. Pour `n = 100`, tu dois obtenir `5050`.

<details>
<summary>💡 Indice (clique pour afficher)</summary>

Comment ferais-tu 1 + 2 + 3 + 4 + 5 avec une calculatrice ? Tu ne tapes pas tout d'un coup : tu gardes un résultat, et tu lui ajoutes le nombre suivant. Ce résultat qui grandit, c'est une variable. Revois l'exemple du `score` dans [Les variables](03-variables-types.md#les-variables), au guide 03.

</details>

## Défi bonus

1. **Le nombre mystère :** fixe un nombre secret dans ton code (`secret = 42`). Demande des essais jusqu'à ce que l'utilisateur trouve, en disant « plus grand » ou « plus petit » à chaque fois. À la fin, affiche le nombre d'essais. (Au bloc 2, on apprendra à choisir le nombre au hasard.)
2. **Le triangle :** demande une hauteur et affiche un triangle d'étoiles :
   ```
   *
   **
   ***
   ****
   ```

   <details>
   <summary>💡 Indice (clique pour afficher)</summary>

   Le défi bonus 3 du [guide 03](03-variables-types.md#défi-bonus) te faisait multiplier un texte par un nombre. Qu'est-ce que ça donnait ? Et quel nombre change à chaque ligne du triangle ?

   </details>

3. **FizzBuzz :** affiche les nombres de 1 à 30, mais remplace les multiples de 3 par `Fizz`, les multiples de 5 par `Buzz`, et les multiples des deux par `FizzBuzz`. C'est un exercice classique d'entrevue d'embauche!

> [!tip] Pour pratiquer encore
> [France-IOI](https://www.france-ioi.org/algo/chapters.php), **niveau 1** du parcours Python : les chapitres sur les répétitions, les variables, les tests et les conditions reprennent exactement ce que tu viens d'apprendre, avec des exercices corrigés automatiquement.

---

Suite : [07 — Les listes](07-listes.md)

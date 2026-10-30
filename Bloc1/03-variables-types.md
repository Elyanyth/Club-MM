# 03 — Variables et types

**Ce que tu vas apprendre :** garder des valeurs en mémoire, faire des calculs, et comprendre pourquoi `"15"` et `15`, ce n'est pas pareil.

---

## Les variables

Une **variable** est une boîte avec une étiquette. On y range une valeur pour la réutiliser plus tard.

```python
age = 15
print(age)
```

- `age` est le **nom** de la variable (l'étiquette).
- `=` veut dire « range dans ». Ce n'est **pas** le « égal » des maths : on lit `age = 15` comme « range 15 dans `age` ».

Une variable peut **changer** de valeur. La nouvelle valeur remplace l'ancienne :

```python
score = 0
score = score + 10
print(score)   # affiche 10
```

La 2ᵉ ligne se lit : « prends la valeur de `score`, ajoute 10, et range le résultat dans `score` ».

> [!tip] Le `#`
> Tout ce qui suit un `#` est un **commentaire** : Python l'ignore. C'est une note pour les humains qui lisent le code.

**Règles pour les noms :** des lettres minuscules, des chiffres et des `_`, sans espace ni accent, et sans commencer par un chiffre. Choisis des noms qui disent ce que la variable contient : `age_dans_10_ans` est bien plus clair que `x`.

> [!tip] Regarde tes variables
> Garde le panneau **View → Variables** ouvert. Après avoir lancé ton programme, il montre chaque variable et sa valeur.

## Les types

Chaque valeur a un **type**, qui dit ce que c'est :

| Type | Ce que c'est | Exemples |
|---|---|---|
| `int` | un nombre entier | `15`, `-3`, `0` |
| `float` | un nombre à virgule (avec un **point**) | `1.72`, `3.0`, `-0.5` |
| `str` | du texte (*string*) | `"Léa"`, `"15"`, `""` |
| `bool` | vrai ou faux | `True`, `False` |

Pour connaître le type d'une valeur, utilise `type`. Essaie dans la console :

```python
type(15)
type("15")
type(1.72)
type(True)
```

## Les opérations

| Opération | Symbole | Exemple | Résultat |
|---|---|---|---|
| Addition | `+` | `7 + 2` | `9` |
| Soustraction | `-` | `7 - 2` | `5` |
| Multiplication | `*` | `7 * 2` | `14` |
| Division | `/` | `7 / 2` | `3.5` |
| Division entière | `//` | `7 // 2` | `3` |
| Reste (modulo) | `%` | `7 % 2` | `1` |
| Puissance | `**` | `7 ** 2` | `49` |

Les comparaisons donnent un `bool` :

```python
15 >= 18    # False
15 < 18     # True
```

## Le piège de `input` : tout est du texte

Écris ce programme et lance-le :

```python
age = input("Quel âge as-tu? ")
print(age + 10)
```

Erreur! Thonny affiche quelque chose comme :

```
TypeError: can only concatenate str (not "int") to str
```

Pourquoi ? **`input` donne toujours du texte** (`str`). Si tu tapes `15`, la variable contient `"15"`, pas `15`. Et Python refuse d'additionner du texte et un nombre.

La solution : **convertir** le texte en nombre avec `int()` :

```python
age = int(input("Quel âge as-tu? "))
print(age + 10)
```

| Fonction | Convertit en | Exemple |
|---|---|---|
| `int()` | entier | `int("15")` donne `15` |
| `float()` | nombre à virgule | `float("1.72")` donne `1.72` |
| `str()` | texte | `str(15)` donne `"15"` |

> [!tip] `int("quinze")`
> Si l'utilisateur tape autre chose qu'un nombre, `int()` provoque une erreur (`ValueError`). Pour l'instant, c'est normal : tape un vrai nombre. On apprendra plus tard à gérer ce cas.

## Afficher proprement avec les f-strings

Pour mélanger du texte et des variables, le plus simple est une **f-string** : un `f` devant les guillemets, et les variables entre accolades `{}`.

```python
nom = "Léa"
age = 15
print(f"{nom} a {age} ans.")
```

Plus besoin de `+` ni de `str()` : Python s'occupe de tout.

### Exercice 1 — Ta carte d'identité, version 2

Reprends `carte.py`. Ajoute :

1. une question pour l'âge, convertie en `int` ;
2. le calcul de l'âge dans 10 ans, rangé dans une variable `age_dans_10_ans` ;
3. une phrase avec une f-string.

```
Comment t'appelles-tu? Léa
Où habites-tu? Sherbrooke
Quel âge as-tu? 15
Salut Léa, de Sherbrooke!
Dans 10 ans, tu auras 25 ans.
```

### Exercice 2 — Encore plus d'infos

Ajoute à ta carte :

1. ta grandeur en mètres (un `float`, par exemple `1.65`), puis affiche-la en centimètres ;
2. une variable `est_majeur` qui vaut `True` ou `False` selon ton âge (indice : `age >= 18`), et affiche-la.

Lance le programme, puis regarde le panneau **Variables** : vérifie le type de chaque valeur.

### Exercice 3 — La calculatrice

Dans un **nouveau** fichier `calcul.py`, demande deux nombres, puis affiche leur somme, leur différence, leur produit et leur quotient.

## Défi bonus

1. Demande un nombre de secondes (par exemple `4000`) et affiche-le en heures, minutes et secondes (`1 h 6 min 40 s`). Indice : `//` et `%` sont tes amis.
2. Demande ton année de naissance et calcule environ combien de jours tu as vécu.
3. Que donne `"ha" * 3` ? Et `"3" + "4"` ? Devine d'abord, puis essaie dans la console.

---

Suite : [04 — Le debugger](04-debugger.md)

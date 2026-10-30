# 05 — Les conditions

**Ce que tu vas apprendre :** faire prendre des décisions à ton programme avec `if`, `elif` et `else`.

---

## `if` : faire quelque chose seulement si…

```python
age = int(input("Quel âge as-tu? "))

if age >= 18:
    print("Tu es majeur.")

print("Merci!")
```

- Après `if`, on écrit une **condition** : une question dont la réponse est `True` ou `False`.
- La ligne finit par **deux-points** `:`.
- Les lignes qui dépendent de la condition sont **décalées vers la droite** (4 espaces, ou la touche **Tab**). C'est ce qu'on appelle l'**indentation**. Thonny la fait pour toi après le `:`.
- `print("Merci!")` n'est pas décalé : il s'exécute **dans tous les cas**.

> [!important] L'indentation compte
> En Python, le décalage n'est pas une question de style : c'est lui qui dit quelles lignes font partie du `if`. Un mauvais décalage change le comportement du programme, ou provoque une erreur `IndentationError`.

## `else` : sinon…

```python
if age >= 18:
    print("Tu es majeur.")
else:
    print("Tu es mineur.")
```

Python exécute **un seul** des deux blocs : celui du `if` si la condition est vraie, sinon celui du `else`.

## `elif` : plusieurs choix

```python
if age < 12:
    print("Tu es un enfant.")
elif age < 18:
    print("Tu es un ado.")
else:
    print("Tu es un adulte.")
```

`elif` veut dire « sinon, si… ». Python teste les conditions **dans l'ordre** et s'arrête à la **première** qui est vraie.

## Les comparaisons

| Symbole | Veut dire | Exemple vrai |
|---|---|---|
| `==` | est égal à | `5 == 5` |
| `!=` | est différent de | `5 != 3` |
| `<` / `>` | plus petit / plus grand | `3 < 5` |
| `<=` / `>=` | plus petit ou égal / plus grand ou égal | `5 >= 5` |

> [!important] `=` ou `==` ?
> `=` **range** une valeur dans une variable. `==` **compare** deux valeurs. Dans un `if`, c'est presque toujours `==`.

On peut aussi comparer du texte : `nom == "Léa"`. Attention, `"léa"` et `"Léa"` ne sont pas égaux pour Python.

## Combiner des conditions : `and`, `or`, `not`

| Opérateur | Vrai quand… | Exemple |
|---|---|---|
| `and` | les deux conditions sont vraies | `age >= 13 and age <= 17` |
| `or` | au moins une est vraie | `ville == "Sherbrooke" or ville == "Magog"` |
| `not` | la condition est fausse | `not est_majeur` |

---

### Exercice 1 — Ta carte d'identité, version 3

Ajoute à `carte.py` :

1. un message « Tu es majeur » ou « Tu es mineur » selon l'âge ;
2. une catégorie avec `elif` : enfant (moins de 12 ans), ado (12 à 17), adulte (18 et plus).

### Exercice 2 — Regarde-le décider

Lance ta carte dans le debugger (`Ctrl+F5`). Quand tu arrives sur un `if`, utilise `F7` (Step into) : Thonny te montre la condition devenir `True` ou `False`, puis saute au bon bloc. Recommence avec un autre âge et compare le chemin suivi.

### Exercice 3 — Pair ou impair

Demande un nombre et dis s'il est pair ou impair. Indice : un nombre pair a un reste de `0` quand on le divise par 2 (`%`).

### Exercice 4 — Le mot de passe

Demande un mot de passe. S'il vaut `"python123"`, affiche « Accès autorisé », sinon « Accès refusé ».

## Défi bonus

1. **Le cinéma :** demande l'âge et le jour de la semaine. Le billet coûte 8 $, mais 5 $ pour les moins de 13 ans, et tout le monde paie 6 $ le mardi (sauf les moins de 13 ans, qui restent à 5 $). Affiche le prix.
2. **Année bissextile :** une année est bissextile si elle est divisible par 4, **sauf** si elle est divisible par 100, **sauf** si elle est aussi divisible par 400. Demande une année et dis si elle est bissextile. Teste avec 2024 (oui), 1900 (non) et 2000 (oui).
3. **Le plus grand :** demande trois nombres et affiche le plus grand, sans utiliser `max`.

---

Suite : [06 — Les boucles](06-boucles.md)

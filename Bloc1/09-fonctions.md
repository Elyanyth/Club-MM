# 09 — Les fonctions

**Ce que tu vas apprendre :** créer tes propres commandes, comme `print` ou `len`, pour ne pas réécrire le même code plusieurs fois.

Tu utilises des fonctions depuis le début : `print`, `input`, `int`, `len`… Quelqu'un les a écrites pour toi. Maintenant, tu vas écrire les tiennes.

---

## Créer une fonction avec `def`

```python
def saluer():
    print("Bonjour!")
    print("Bienvenue au club.")

saluer()
saluer()
```

- `def` veut dire « définis ». Il est suivi du **nom** de la fonction, de parenthèses et de `:`.
- Les lignes décalées forment le **corps** de la fonction.
- Écrire `def` ne lance **rien** : ça apprend seulement la fonction à Python. Elle s'exécute quand on l'**appelle** : `saluer()`.

> [!important] Définir avant d'appeler
> Python lit ton fichier de haut en bas. Si tu appelles `saluer()` **avant** la ligne `def saluer():`, tu obtiens `NameError: name 'saluer' is not defined`. Mets tes fonctions en haut du fichier.

## Les paramètres : donner des informations à la fonction

```python
def saluer(nom):
    print(f"Bonjour {nom}!")

saluer("Léa")
saluer("Noah")
```

`nom` est un **paramètre** : une variable qui reçoit la valeur qu'on met entre parenthèses à l'appel. Au premier appel, `nom` vaut `"Léa"` ; au deuxième, `"Noah"`.

Une fonction peut avoir plusieurs paramètres, séparés par des virgules :

```python
def presenter(nom, age):
    print(f"{nom} a {age} ans.")

presenter("Léa", 15)
```

## `return` : faire **donner** une réponse à la fonction

Certaines fonctions font quelque chose (`print` affiche). D'autres **donnent** un résultat qu'on peut ranger dans une variable (`len("Léa")` donne `3`). Pour ça, on utilise `return` :

```python
def carre(n):
    return n * n

resultat = carre(7)
print(resultat)          # 49
print(carre(3) + 1)      # 10
```

- `return` renvoie la valeur à l'endroit où la fonction a été appelée. `carre(7)` est **remplacé** par `49`.
- `return` **arrête** la fonction : les lignes en dessous ne s'exécutent pas.

> [!important] `print` ou `return` ?
> `print` **affiche** une valeur à l'écran, pour l'humain. `return` **donne** une valeur au programme, pour qu'il continue à s'en servir. Une fonction sans `return` donne `None` (« rien »). Si tu vois `None` s'afficher là où tu attendais un nombre, c'est presque toujours un `return` oublié.

## La portée : ce qui se passe dans la fonction reste dans la fonction

```python
def calculer_total(prix, quantite):
    total = prix * quantite
    return total

calculer_total(5, 3)
print(total)
```

Erreur! `NameError: name 'total' is not defined`. Les variables créées **dans** une fonction (et ses paramètres) sont **locales** : elles existent seulement pendant que la fonction s'exécute, puis disparaissent. Pour récupérer le résultat, il faut le ranger : `total = calculer_total(5, 3)`.

C'est une bonne chose : tu peux appeler tes variables `total` ou `i` dans dix fonctions différentes sans qu'elles se mélangent.

## Voir une fonction s'exécuter dans le debugger

C'est là que Thonny brille. Écris ce programme dans `fonctions.py` :

```python
def carre(n):
    resultat = n * n
    return resultat

a = carre(4)
b = carre(a)
print(b)
```

1. Lance le debugger (`Ctrl+F5`). Remarque que `F6` **saute** par-dessus le `def` : la fonction est seulement définie.
2. Sur la ligne `a = carre(4)`, appuie sur `F7` (Step into) plusieurs fois. Quand tu entres dans la fonction, Thonny **ouvre une nouvelle fenêtre** avec le code de la fonction et **ses propres variables** : `n` vaut `4`.
3. Continue avec `F7` : la fenêtre se ferme au `return`, et `carre(4)` est remplacé par `16` dans la fenêtre principale.
4. Au deuxième appel, regarde : `n` vaut maintenant `16`. Même fonction, autre valeur.

Remarque que `n` et `resultat` n'apparaissent **jamais** dans le panneau Variables de la fenêtre principale : c'est la portée, en direct.

---

### Exercice 1 — Tes premières fonctions

Écris et teste ces fonctions. Chacune utilise `return` (pas de `print` à l'intérieur!) :

1. `double(n)` donne le double de `n` ;
2. `est_pair(n)` donne `True` si `n` est pair, sinon `False` ;
3. `plus_grand(a, b)` donne le plus grand des deux nombres, sans utiliser `max`.

Teste chacune avec plusieurs valeurs, par exemple `print(est_pair(4), est_pair(7))`.

### Exercice 2 — Le bug du `None`

Ce programme calcule le prix d'un article en solde à 20 % de rabais. Il devrait afficher `Prix en solde : 40.0 $`. Il affiche `40.0`, puis `Prix en solde : None $`. Trouve le bug avec le debugger (`F7` pour entrer dans la fonction), puis corrige-le.

```python
def en_solde(prix):
    nouveau_prix = prix * 0.8
    print(nouveau_prix)

prix_final = en_solde(50)
print(f"Prix en solde : {prix_final} $")
```

### Exercice 3 — Les listes en paramètre

Écris une fonction `moyenne(notes)` qui reçoit une **liste** de nombres et donne leur moyenne. Réutilise ton code de l'exercice 3 du [guide 07](07-listes.md). Teste-la avec deux listes différentes.

### Exercice 4 — Ta carte d'identité, version 7

Range ta carte en fonctions. Par exemple :

1. `demander_age()` pose la question, redemande tant que l'âge n'est pas valide (guide 06) et **donne** l'âge ;
2. `categorie(age)` donne `"enfant"`, `"ado"` ou `"adulte"` (guide 05) ;
3. `afficher_carte(carte)` reçoit ton dictionnaire (guide 08) et l'affiche.

Le programme principal, en bas du fichier, ne fait plus qu'appeler tes fonctions. Il devrait tenir en quelques lignes et se lire presque comme une phrase.

## Défi bonus

1. **Le mot de passe solide :** écris `est_solide(mdp)`, qui donne `True` si le mot de passe a au moins 8 caractères **et** contient au moins un chiffre. Pour savoir si un caractère est un chiffre, utilise `isdigit` : `"5".isdigit()` donne `True`, et `"a".isdigit()` donne `False`.
2. **Les valeurs par défaut :** un paramètre peut avoir une valeur par défaut : `def saluer(nom, langue="fr"):`. Écris une fonction `saluer` qui dit « Bonjour » ou « Hello » selon la langue, et appelle-la avec et sans le 2ᵉ argument.
3. **La fonction qui s'appelle elle-même :** devine ce que fait ce programme, puis vérifie avec `F7`. Combien de fenêtres Thonny ouvre-t-il ?
   ```python
   def decompte(n):
       if n == 0:
           print("Décollage!")
       else:
           print(n)
           decompte(n - 1)

   decompte(3)
   ```
   Ça s'appelle la **récursivité**. On la reverra au bloc 2.

---

Suite : [10 — Mini-projet](10-mini-projet.md)

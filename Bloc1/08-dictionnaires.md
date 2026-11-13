# 08 — Les dictionnaires

**Ce que tu vas apprendre :** ranger des valeurs sous un **nom** plutôt qu'à une position.

Dans une liste, on retrouve une valeur par son indice : `infos[2]`. Mais qu'est-ce qu'il y a à l'indice 2, déjà ? L'âge ? La ville ? Un **dictionnaire** règle ce problème : chaque valeur a une étiquette.

---

## Créer un dictionnaire

```python
personne = {
    "nom": "Léa",
    "age": 15,
    "ville": "Sherbrooke",
}
print(personne["nom"])   # Léa
```

- Un dictionnaire s'écrit entre **accolades** `{ }`.
- Chaque élément est une paire **clé : valeur**. Ici, `"nom"` est la clé et `"Léa"` est la valeur.
- On accède à une valeur avec sa clé entre crochets : `personne["age"]`.

C'est comme un vrai dictionnaire : tu cherches un mot (la clé) et tu trouves sa définition (la valeur).

## Ajouter, modifier, enlever

```python
personne["age"] = 16          # modifie : la clé existe déjà
personne["jeu"] = "Zelda"     # ajoute : la clé n'existait pas
del personne["ville"]         # enlève la clé et sa valeur
```

Même écriture pour ajouter et modifier : si la clé existe, la valeur est remplacée, sinon elle est créée.

> [!important] `KeyError`
> `personne["courriel"]` provoque une erreur `KeyError: 'courriel'` si cette clé n'existe pas. Pour vérifier avant, utilise `in` : `if "courriel" in personne:`. Ou utilise `get`, qui donne une valeur par défaut au lieu de planter : `personne.get("courriel", "aucun")`.

## Parcourir un dictionnaire

```python
prix = {"pomme": 1.25, "banane": 0.50, "lait": 4.99}

for article in prix:
    print(article)                        # les clés

for article, montant in prix.items():
    print(f"{article} : {montant} $")     # les clés ET les valeurs
```

`prix.items()` donne les paires une à une. À chaque tour, la première variable reçoit la clé et la deuxième, la valeur.

## Liste ou dictionnaire ?

- Des éléments **du même genre**, dans un ordre (des notes, des joueurs, des loisirs) ? → **liste**.
- Des informations **différentes** sur une même chose (le nom, l'âge et la ville d'une personne) ? → **dictionnaire**.

Et on peut les combiner! Une liste de dictionnaires, c'est la façon classique de représenter une collection de choses :

```python
amis = [
    {"nom": "Léa", "age": 15},
    {"nom": "Noah", "age": 14},
]
for ami in amis:
    print(f"{ami['nom']} a {ami['age']} ans.")
```

> [!tip] Les guillemets dans une f-string
> Dans `f"…{ami['nom']}…"`, la clé utilise des guillemets **simples** `'nom'`, parce que la f-string utilise déjà les doubles. En Python, `'nom'` et `"nom"` veulent dire la même chose.

---

### Exercice 1 — Ta carte d'identité, version 6

Réorganise `carte.py` : au lieu d'avoir plein de variables séparées, range toutes les réponses dans **un seul** dictionnaire `carte`, avec les clés `"nom"`, `"ville"`, `"age"` et `"loisirs"` (la valeur de `"loisirs"` est ta liste du guide 07!).

À la fin, affiche toute la carte avec une boucle sur `carte.items()`.

```
nom : Léa
ville : Sherbrooke
age : 15
loisirs : ['soccer', 'dessin', 'jeux vidéo']
```

Lance-la dans le debugger et regarde `carte` se remplir dans le panneau **Variables**.

### Exercice 2 — Le traducteur

Crée un dictionnaire français → anglais d'au moins 5 mots (`{"chat": "cat", "chien": "dog", …}`). Demande un mot :

- s'il est dans le dictionnaire, affiche sa traduction ;
- sinon, affiche « Je ne connais pas ce mot ».

Puis fais-le tourner en boucle jusqu'à ce que l'utilisateur tape `fin`.

### Exercice 3 — Le compteur de lettres

Demande une phrase et compte combien de fois chaque lettre apparaît. Le résultat est un dictionnaire : pour `"bonbon"`, tu dois obtenir `{"b": 2, "o": 2, "n": 2}`.

<details>
<summary>💡 Indice (clique pour afficher)</summary>

Imagine que tu comptes à la main, avec une feuille et un crayon. Tu lis une lettre et tu regardes ta feuille : que fais-tu si la lettre y est déjà ? Et si elle n'y est pas encore ? Revois [Ajouter, modifier, enlever](#ajouter-modifier-enlever), et l'encadré `KeyError` juste en dessous. Teste avec `"bonbon"` dans le debugger.

</details>

### Exercice 4 — Le panier

Avec le dictionnaire `prix` de la section « Parcourir », et une liste `panier = ["pomme", "lait", "pomme", "banane"]`, calcule le total à payer.

## Défi bonus

1. **Le carnet de notes :** un dictionnaire où chaque clé est une matière et chaque valeur, une **liste** de notes (`{"maths": [80, 75], "français": [90]}`). Affiche la moyenne de chaque matière. Puis permets à l'utilisateur d'ajouter une note dans une matière (existante ou nouvelle).
2. **Le mot le plus fréquent :** à partir de ton compteur de l'exercice 3, adapte-le pour compter les **mots** d'une phrase plutôt que les lettres, puis affiche le mot le plus fréquent. Pour découper une phrase en mots, utilise `split` : `"le chat dort".split()` donne `["le", "chat", "dort"]`.

## Pour aller plus loin : tuples et ensembles

- Un **tuple** est une liste qu'on ne peut pas modifier, écrite avec des parenthèses : `point = (3, 5)`. Pratique pour des valeurs qui vont ensemble et ne changent pas (des coordonnées, une date).
- Un **ensemble** (*set*) est une collection **sans doublons** et sans ordre : `set(["a", "b", "a"])` donne `{"a", "b"}`. Pratique pour éliminer les doublons d'une liste. Essaie-le sur ta liste d'épicerie du guide 07.

---

Suite : [09 — Les fonctions](09-fonctions.md)

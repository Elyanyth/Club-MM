# CLAUDE.md

## Aider l'élève dans un exercice : indice ou information ?

Avant d'ajouter de l'aide à un exercice, pose-toi une question : **est-ce qu'un guide précédent (ou plus haut dans le même guide) a déjà enseigné ça ?**

- **Oui** → c'est un **indice**. Il est caché, et il pousse l'élève dans la bonne direction sans donner la réponse.
- **Non** → c'est une **information nouvelle**. Elle est visible, dans l'énoncé de l'exercice. L'élève ne peut pas la deviner : la cacher ne sert à rien.

### Les indices

Un indice est un **coup de pouce** : l'élève doit encore réfléchir pour trouver la solution. Un bon indice peut :

- renvoyer à la section du guide qui contient ce qu'il faut, avec un lien cliquable (par exemple `[Les opérations](#les-opérations)`, ou `[guide 06](06-boucles.md#while-ou-for-)`) ;
- réexpliquer une notion autrement ;
- proposer une autre façon d'aborder le problème, ou poser une question qui guide (par exemple : « Imagine que tu le fais à la main, sur papier… »).

Un indice ne contient **jamais** la réponse, ni en code ni en mots : pas de ligne de code à recopier, pas d'algorithme décrit étape par étape.

Tout indice est **caché** dans un bloc `<details>` (GitHub l'affiche comme une section à cliquer) :

```markdown
<details>
<summary>💡 Indice (clique pour afficher)</summary>

Le texte de l'indice, en Markdown.

</details>
```

- Garde les lignes vides après `<summary>` et avant `</details>` : sans elles, GitHub n'interprète pas le Markdown à l'intérieur.
- Dans un élément de liste (défis bonus numérotés, par exemple), indente tout le bloc `<details>` comme le texte de l'élément (3 espaces pour `1.`, 2 pour `-`), avec une ligne vide avant, pour qu'il reste attaché à l'élément.
- N'utilise pas `> [!tip]` pour un indice.

### Les informations nouvelles

Une fonction, une méthode ou une astuce qu'aucun guide n'a encore enseignée (par exemple `len()`, `.split()`, `.isdigit()`) est écrite **dans l'énoncé**, visible, avec un court exemple : « `len("Léa")` donne `3`. » Si elle mérite plus qu'une phrase, utilise un encadré `> [!tip]` juste avant ou après l'énoncé.

Les encadrés `> [!tip]` et `> [!important]` servent aux explications que tout le monde doit lire, jamais aux indices.

### Les liens vers une section

GitHub crée l'ancre d'un titre ainsi : tout en minuscules, les accents gardés, la ponctuation et les backticks enlevés, chaque espace remplacée par `-`. Par exemple, ``## `while` ou `for` ?`` devient `#while-ou-for-`.

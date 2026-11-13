# 10 — Mini-projet : le quiz

**Ce que tu vas faire :** construire un vrai programme du début à la fin, en utilisant **tout** ce que tu as appris dans le bloc 1.

Ce guide ne t'apprend pas de nouvelle notion. Il te guide étape par étape, mais c'est toi qui écris le code. Tu vas sûrement bloquer à certains moments : c'est normal, et c'est le but. Relis le guide de la notion, utilise le debugger 🐞, demande à ton voisin.

> [!important] La règle de l'IA
> Tu peux demander à une IA de **t'expliquer** une erreur ou une notion. Tu ne lui demandes pas d'écrire ton quiz : c'est **ton** projet.

---

## Le projet

Un quiz sur le sujet de ton choix (jeux vidéo, sport, animaux, ta série préférée…). Le programme :

1. pose une série de questions, une à la fois ;
2. dit si chaque réponse est bonne ou mauvaise, et donne la bonne réponse au besoin ;
3. affiche le score à la fin, avec un message selon le résultat ;
4. propose de rejouer.

```
=== Quiz : les animaux ===

Question 1 : Quel est le plus grand mammifère?
> la baleine bleue
Bonne réponse!

Question 2 : Combien de pattes a une araignée?
> 6
Oups! La bonne réponse était : 8

Score : 1 / 2
Pas mal! Continue de t'entraîner.

Veux-tu rejouer? (oui/non) non
Merci d'avoir joué!
```

Crée un nouveau fichier `quiz.py`. Fais **une étape à la fois**, et lance ton programme après chaque étape pour vérifier qu'il marche avant de continuer.

## Étape 1 — Une seule question

Écris le programme pour **une** question : afficher la question, demander la réponse, dire si elle est bonne.

*Notions : `print`, `input`, `if` / `else` (guides 02 et 05).*

> [!tip] Majuscules et espaces
> Si la réponse attendue est `"8"` et que l'utilisateur tape `" 8"`, ce n'est pas égal. Même chose pour `"Paris"` et `"paris"`. Deux outils t'aident : `reponse.strip()` enlève les espaces au début et à la fin, et `reponse.lower()` met tout en minuscules. Essaie-les dans la console.

## Étape 2 — Les questions dans une liste

Range tes questions dans une **liste de dictionnaires**, un dictionnaire par question :

```python
questions = [
    {"question": "Quel est le plus grand mammifère?", "reponse": "la baleine bleue"},
    {"question": "Combien de pattes a une araignée?", "reponse": "8"},
]
```

Ajoute au moins 5 questions. Puis utilise une boucle `for` pour les poser toutes, une à la fois.

*Notions : listes, dictionnaires, `for` (guides 06, 07 et 08).*

> [!tip] Vérifie avec le debugger
> Lance ton quiz avec 🐞 et avance avec `F6`. À chaque tour de boucle, regarde dans le panneau Variables quel dictionnaire est dans ta variable.

## Étape 3 — Le score

Compte les bonnes réponses dans une variable `score`. À la fin, affiche `Score : 3 / 5`. Le `5` ne doit pas être écrit à la main : si tu ajoutes une question, il doit changer tout seul.

Ajoute ensuite un message selon le résultat : parfait, bien, à retravailler…

*Notions : variables, `len`, `if` / `elif` / `else` (guides 03, 05 et 07).*

## Étape 4 — Des fonctions

Ton programme grossit. Range-le en fonctions, par exemple :

- `poser_question(q)` reçoit **un** dictionnaire, pose la question et donne `True` si la réponse est bonne, `False` sinon ;
- `jouer(questions)` pose toutes les questions et **donne** le score ;
- `afficher_resultat(score, total)` affiche le score et le message.

Ton programme principal, en bas, devient très court.

*Notions : `def`, paramètres, `return` (guide 09).*

## Étape 5 — Rejouer

À la fin, demande « Veux-tu rejouer? ». Tant que la réponse est `oui`, relance le quiz.

*Notions : `while` (guide 06).*

---

## Améliorations

Ton quiz fonctionne ? Bravo! Choisis les améliorations qui te tentent, dans l'ordre que tu veux :

1. **Plusieurs bonnes réponses :** `"reponses": ["8", "huit"]` au lieu d'une seule réponse.

   <details>
   <summary>💡 Indice (clique pour afficher)</summary>

   Tu as maintenant une liste de bonnes réponses. Au [guide 07](07-listes.md#modifier-une-liste), tu as vu comment savoir si une valeur se trouve dans une liste.

   </details>

2. **Choix multiples :** ajoute une clé `"choix"` avec une liste d'options, affiche-les numérotées (`1. Paris`, `2. Lyon`…) et demande le numéro.
3. **Des points différents :** une clé `"points"` pour les questions plus difficiles.
4. **Les erreurs à revoir :** garde dans une liste les questions ratées et réaffiche-les à la fin.
5. **Le meilleur score :** garde le meilleur score entre les parties et annonce quand il est battu.
6. **Deux joueurs :** chacun répond à son tour, et le programme annonce le gagnant.

## Tu préfères une autre idée ?

Tu peux faire un autre projet de taille semblable, à condition d'en parler à l'animateur avant de commencer. Quelques idées :

- **Le nombre mystère, version complète :** reprends le défi du guide 06 avec des fonctions, un nombre d'essais limité, des niveaux de difficulté et un tableau des meilleurs scores.
- **Le gestionnaire de notes :** un menu (ajouter une note, voir les moyennes, quitter) qui revient tant qu'on ne quitte pas.
- **L'aventure dont tu es le héros :** une histoire où chaque choix mène à une autre scène.

  <details>
  <summary>💡 Indice (clique pour afficher)</summary>

  Chaque scène a un texte et des choix, et chaque choix mène à une autre scène. Relis [Liste ou dictionnaire ?](08-dictionnaires.md#liste-ou-dictionnaire-) au guide 08 : quelle structure te permet de retrouver une scène par son nom ?

  </details>

Peu importe le projet, la règle est la même : **une version minimale qui fonctionne d'abord**, les améliorations ensuite.

## Pour aller plus loin : les erreurs de saisie

Si ton quiz demande un nombre (pour les choix multiples) et que l'utilisateur tape `allo`, `int()` plante avec `ValueError`. On peut **attraper** l'erreur avec `try` / `except` :

```python
try:
    choix = int(input("Ton choix : "))
except ValueError:
    print("Ce n'est pas un nombre!")
```

Python **essaie** le bloc `try`. Si une `ValueError` se produit, au lieu de planter, il exécute le bloc `except`. Combine-le avec une boucle `while` pour redemander jusqu'à obtenir un vrai nombre.

---

## Tu as fini le bloc 1!

Bravo! Tu connais maintenant les briques de base de **tous** les langages de programmation : variables, conditions, boucles, listes, dictionnaires et fonctions. Le reste, c'est de les combiner.

- **Montre ton quiz** à ton voisin et fais-le jouer. Regarde où il bloque : c'est souvent là qu'il y a une amélioration à faire.
- [France-IOI](https://www.france-ioi.org/algo/chapters.php) : continue avec le **niveau 2** du parcours Python.
- [Exercism, piste Python](https://exercism.org/tracks/python) : des exercices avec des commentaires sur ton code.
- **Aide les autres :** explique une notion à quelqu'un qui bloque. Montre-lui comment utiliser le debugger plutôt que de lui donner la réponse.

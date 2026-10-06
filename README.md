# Plan de club — Club de technologie informatique

## C'est quoi le club ?

Le club t'apprend à programmer, de ta toute première ligne de code jusqu'à ton propre projet, puis à travailler avec les outils d'IA qu'utilisent aujourd'hui les développeurs. Aucune expérience n'est requise : on part de zéro, et si tu as déjà programmé, une piste avancée t'attend.

- **Qui ?** Les élèves du secondaire (14 à 18 ans), débutants comme avancés.
- **Quand ?** Une rencontre par semaine, tout au long de l'année.
- **Avec quoi ?** Ton portable Windows. On installe tout ensemble.
- **Langage :** Python, du début à la fin.
- **Pas de notes.** On est là pour apprendre et construire. Un certificat de participation mentionnant ton projet final peut t'être remis à la fin de l'année.

> [!important] La règle de l'IA
> Jusqu'au bloc 5, l'IA (ChatGPT, Claude, etc.) peut **t'expliquer** une notion ou une erreur, comme le ferait un tuteur. Elle ne **code pas à ta place**.
> Pourquoi ? Pour utiliser l'IA efficacement plus tard, tu dois être capable de comprendre et de vérifier ce qu'elle produit. C'est exactement ce que les blocs 1 à 4 t'apprennent.

### Comment ça fonctionne

- **Tu as manqué une semaine ?** Pas de panique : chaque rencontre commence par un court rappel, et les ressources de chaque semaine te permettent de rattraper.
- **Tronc commun + piste avancée :** tout le monde voit les mêmes notions. Si tu finis vite, tu as des défis bonus, du matériel supplémentaire et la section « Pour aller plus loin ».
- **Entraide :** si tu es à l'aise, aider ton voisin est la meilleure façon de consolider ce que tu sais.
- **Le rythme est indicatif :** les durées ci-dessous sont approximatives et s'ajusteront selon le groupe et ce que vous voulez faire.

---

## Bloc 1 — Les bases (~7 semaines)

**Objectif :** écrire tes premiers programmes et comprendre les briques de base de tout langage.
**Outil :** [Thonny](https://thonny.org), un éditeur Python simple pour débutants. Si tu ne peux pas l'installer, on utilise un éditeur en ligne.

1. Installation, premier programme, `print` et `input`
2. Variables et types (`int`, `float`, `str`, `bool`), opérations
3. Conditions : `if` / `elif` / `else`, opérateurs logiques
4. Boucles : `while`, `for`, `range`
5. Listes et dictionnaires
6. Fonctions : paramètres, `return`, portée
7. Mini-projet récapitulatif (jeu de devinettes, quiz…)

**Pour aller plus loin :** compréhensions de listes, tuples et sets, gestion d'erreurs (`try` / `except`).

---

## Bloc 2 — Scripting et algorithmes (~6 semaines)

**Objectif :** faire travailler l'ordinateur pour toi, et apprendre à réfléchir comme un programmeur.

1. Modules et bibliothèque standard (`random`, `math`, `datetime`)
2. Lire et écrire des fichiers (texte, CSV)
3. Automatisation : manipuler des fichiers et des dossiers (`os`, `pathlib`), par exemple renommer 100 photos d'un coup
4. Penser en algorithme : décomposer un problème, pseudocode, recherche linéaire et binaire
5. Le tri : du tri à bulles à `sorted()`, notion d'efficacité
6. Défi algorithmique en équipe

**Pour aller plus loin :** récursivité, notation Big-O, problèmes de l'[Advent of Code](https://adventofcode.com).

---

## Bloc 3 — Les outils des développeurs (~3 semaines)

**Objectif :** quitter Thonny et travailler avec les mêmes outils que les professionnels.

1. [VS Code](https://code.visualstudio.com) et le terminal : naviguer, lancer un script, utiliser le débogueur
2. Git : sauvegarder ton travail avec des commits, consulter l'historique
3. [GitHub](https://github.com) : mettre ton code en ligne, collaborer, installer des bibliothèques avec `pip`

**Pour aller plus loin :** branches, pull requests, environnements virtuels.

---

## Bloc 4 — Ton projet (~7 semaines)

**Objectif :** construire quelque chose qui t'appartient, du début à la fin.

- **Solo ou en équipe**, et **sujet libre**, à condition d'obtenir l'accord de l'animateur.
- **Fiche de projet** à remettre au plus tard à la fin de la première semaine du bloc (une discussion avec l'animateur peut aussi faire l'affaire) :
  - ton idée, en une phrase ;
  - la **version minimale**, c'est-à-dire ce qui doit absolument fonctionner ;
  - les **extensions**, si le temps le permet ;
  - solo ou en équipe (et avec qui).

> [!tip] Choisir la bonne taille
> L'erreur la plus courante est de viser trop gros. Une version minimale qui fonctionne vaut mieux qu'un projet ambitieux inachevé. Quelques exemples de bonne taille : un jeu en 2D avec Pygame, un outil qui organise automatiquement tes fichiers, un petit site web avec Flask, un analyseur de données à partir d'un fichier CSV.

---

## Bloc 5 — Programmer avec l'IA (~4 semaines)

**Objectif :** utiliser les agents de code dans l'IDE (comme Claude Code, Codex ou GitHub Copilot) de façon efficace et responsable.

1. **C'est quoi un agent de code ?** Les tokens, la fenêtre de contexte, et la différence entre *smart zone* et *dumb zone* : plus la conversation se remplit, moins l'IA est fiable.
2. **Donner du contexte :** les fichiers d'instructions persistantes (`AGENTS.md`, `CLAUDE.md`) et les *skills*.
3. **Un bon workflow :** rechercher → planifier → implémenter → réviser. Faire des commits fréquents, relire chaque modification et respecter les règles de sécurité :
   - toujours partir d'un dépôt Git propre ;
   - approuver les commandes avant qu'elles soient exécutées ;
   - ne jamais mettre de mots de passe ni de clés dans ton projet.
4. **Pratique :** ajouter une fonctionnalité à ton projet avec un agent, en suivant le workflow.

**Outils :** l'animateur fait les démonstrations. Pour pratiquer, tu utilises un outil gratuit permis à ton âge (par exemple GitHub Copilot dans VS Code). Certains outils, comme Claude, sont réservés aux 18 ans et plus.

**Pour aller plus loin :** écrire ton propre skill, comparer deux outils sur la même tâche.

---

## Finale — Démo des projets (1 semaine)

Tu présentes ton projet au groupe : la version construite « à la main » et ce que l'agent t'a permis d'y ajouter.

---

## Ressources pour pratiquer

- [France-IOI](https://www.france-ioi.org) : exercices progressifs en français
- [Exercism, piste Python](https://exercism.org/tracks/python) : exercices avec corrections commentées
- [Codewars](https://www.codewars.com) : petits défis classés par difficulté
- [Advent of Code](https://adventofcode.com) : énigmes algorithmiques
- [Documentation officielle de Python](https://docs.python.org/fr/3/tutorial/) : le tutoriel officiel, en français

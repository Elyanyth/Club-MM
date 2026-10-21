# 03 — Le skill `teach`

## C'est quoi un skill ?

Un **skill** est un fichier d'instructions qui apprend à l'IA une façon précise de travailler. Quand tu lui demandes d'utiliser un skill, elle lit ces instructions et les suit.

Le skill **`teach`** a été écrit par [Matt Pocock](https://github.com/mattpocock/skills), un formateur reconnu en programmation. Il transforme l'IA en **tuteur** qui t'accompagne sur plusieurs séances.

## Comment `teach` t'enseigne

- **Il commence par ta mission.** Avant d'enseigner quoi que ce soit, il te demande *pourquoi* tu veux apprendre ce sujet. Toutes les leçons sont ensuite liées à cet objectif.
- **Il cherche de bonnes sources.** Il s'appuie sur des ressources fiables (documentation officielle, bons tutoriels) plutôt que sur sa mémoire, et il les cite.
- **Il fait des leçons courtes.** Chaque leçon est une page web qui enseigne **une seule chose**, avec un petit quiz ou un exercice.
- **Il te fait travailler ta mémoire.** Il te demande de te rappeler les notions au lieu de les relire, et revient sur les anciennes notions au fil du temps. C'est plus exigeant, mais c'est ce qui fait que tu t'en souviens longtemps.
- **Il se souvient de toi.** Il note ce que tu as appris et ce que tu préfères, et reprend où tu étais rendu à la séance suivante.

Tout ça est enregistré dans des fichiers, dans ton dossier d'apprentissage :

| Fichier ou dossier | Contenu |
|---|---|
| `MISSION.md` | Pourquoi tu veux apprendre ce sujet. |
| `RESOURCES.md` | Les sources fiables qu'il a trouvées. |
| `lessons/` | Tes leçons (pages web à ouvrir dans ton navigateur). |
| `reference/` | Des aide-mémoires à consulter et à imprimer. |
| `learning-records/` | Ce que tu as appris, séance après séance. |
| `NOTES.md` | Ses notes sur tes préférences. |
| `assets/` | Le style et les quiz partagés par les leçons. |

> [!tip] Ces fichiers sont à toi
> Tu peux les ouvrir, les lire et même les corriger. Si `MISSION.md` ne correspond plus à ce que tu veux, dis-le à l'IA.

## Installer `teach`

Dans VS Code, ouvre un terminal (**Terminal → New Terminal**) et exécute :

```powershell
npx skills@latest add mattpocock/skills -a opencode -g --skill teach -y
```

- Si on te demande « Need to install the following packages… Ok to proceed? », tape `y` puis **Entrée**.
- `-g` installe le skill pour **tous tes dossiers**, pas seulement le dossier ouvert.

Vérifie que l'installation a fonctionné :

```powershell
Test-Path "$env:USERPROFILE\.agents\skills\teach\SKILL.md"
```

Tu dois voir `True`.

> [!tip] Installer tous les skills de Matt Pocock
> Le dépôt contient une trentaine d'autres skills, surtout pour programmer avec l'IA (planifier, réviser du code, déboguer…). Tu n'en as pas besoin maintenant, mais ils seront utiles au bloc 5. Pour tout installer d'un coup :
> ```powershell
> npx skills@latest add mattpocock/skills -a opencode -g --skill '*' -y
> ```
> Pour voir la liste avant d'installer :
> ```powershell
> npx skills@latest add mattpocock/skills --list
> ```

### Si la commande `npx` ne fonctionne pas

Si ton ordinateur est géré par l'école, essaie d'abord avec `npx.cmd` au lieu de `npx`. Si ça ne fonctionne toujours pas, installe le skill à la main :

1. Télécharge le dépôt : [github.com/mattpocock/skills/archive/refs/heads/main.zip](https://github.com/mattpocock/skills/archive/refs/heads/main.zip).
2. Ouvre le fichier `.zip` et va dans `skills-main\skills\productivity\`.
3. Dans le terminal, ouvre le dossier des skills d'OpenCode :

   ```powershell
   New-Item -ItemType Directory -Force "$env:USERPROFILE\.config\opencode\skills"
   explorer "$env:USERPROFILE\.config\opencode\skills"
   ```

4. Copie **le dossier `teach` au complet** dans la fenêtre qui vient de s'ouvrir. Il doit contenir `SKILL.md` et les autres fichiers `*-FORMAT.md`.

Tu dois obtenir `...\.config\opencode\skills\teach\SKILL.md`.

## Ta première séance

### 1. Un dossier par sujet

`teach` utilise le dossier ouvert comme **espace d'apprentissage**. Crée donc un dossier par sujet dans `Documents\Apprentissage`, par exemple :

```
Documents\Apprentissage\python\
Documents\Apprentissage\git\
```

Ne mélange pas deux sujets dans le même dossier.

### 2. Ouvrir le dossier et lancer OpenCode

1. Dans VS Code : **File → Open Folder…** et choisis ton dossier de sujet (par exemple `Apprentissage\python`).
2. **Terminal → New Terminal**, puis :

   ```powershell
   opencode
   ```

### 3. Démarrer `teach`

Écris ce message, en remplaçant le sujet :

```
Utilise le skill teach. Je veux apprendre les bases de Python.
```

L'IA va :

1. te poser des questions sur ta **mission**. Réponds honnêtement : « pour le club », « pour faire un jeu », « parce que c'est au programme »… Plus ta réponse est précise, meilleures seront les leçons ;
2. chercher des sources fiables ;
3. créer ta première leçon dans `lessons/`.

> [!important] Quand OpenCode te demande la permission
> OpenCode peut te demander d'accepter une action (exécuter une commande, modifier un fichier hors du dossier…). **Lis ce qu'il veut faire avant d'accepter.** Si tu ne comprends pas, refuse et demande-lui d'expliquer, ou demande à l'animateur.

### 4. Faire la leçon

Les leçons sont des pages web. Pour en ouvrir une, va dans le dossier `lessons` avec l'Explorateur de fichiers et double-clique sur le fichier `.html`. Elle s'ouvre dans ton navigateur.

Fais la leçon et le quiz, puis reviens dans OpenCode pour :

- dire comment ça s'est passé (« j'ai eu 3/4, je n'ai pas compris la question 2 ») ;
- poser **toutes** tes questions. L'IA est ton tuteur : demande-lui d'expliquer autrement, de donner un autre exemple, etc.

### 5. Les séances suivantes

Ouvre le même dossier, lance `opencode` et écris :

```
Utilise le skill teach. On continue.
```

L'IA relit tes fichiers et reprend où tu étais rendu.

## Bien utiliser tes requêtes

Rappel : la limite quotidienne est **partagée par tout le club** et chaque étape de l'IA compte (voir l'[aperçu](00-apercu.md#ce-que-gratuit-veut-dire)).

- La **première séance** d'un sujet est la plus coûteuse : l'IA cherche des sources et crée plusieurs fichiers. Les suivantes coûtent moins cher.
- Le gros de l'apprentissage se fait **dans la leçon**, dans ton navigateur, et ça ne coûte aucune requête.
- Regroupe tes questions dans un seul message plutôt que d'en envoyer cinq petits.
- Ne relance pas la même demande en boucle si l'IA est lente : attends sa réponse.

> [!tip] Si l'IA se met à répondre en anglais
> Rappelle-lui simplement : « Réponds en français, s'il te plaît. » Si ça arrive souvent, vérifie que ton fichier `AGENTS.md` existe ([guide 02, étape 6](02-opencode.md#6-les-règles-du-tuteur)).

# Développement web avancé - 3e année

Ce dépôt vous accompagnera tout au long du cours de cette année.

## Pré-requis

Afin de pouvoir faire du "développement web avancé", nous devons commencer par configurer un environnement "kivabien".

En effet, notre workflow "moderne" nous amènera à utiliser la __ligne de commande__, via un __terminal__, dans un __environnement JS__, à l'aide d'une solution de __gestion de versions__.

Nous aurons donc besoin de :

1. Terminal (Terminal, iTerm, …)
2. Environnement JS :
    - `node`
    - `nvm`
    - `npm`
3. Git

## Terminal

Logiciel qui permet d'émuler un ou plusieurs __terminaux informatiques__ sur notre machine.
Grâce à ce terminal, nous pourrons ouvrir un __shell__.
Un shell est une interface permettant de communiquer avec le système d'exploitation via __CLI__ (Interface en ligne de commande).
Les plus connus sont `bash` et `zsh` (ou PowerShell sous Windows).

Dit autrement, c'est ce qui vous permet de rentrer dans la matrice en mode "Mr Robot"…

> Sous Mac OS X, vous pouvez utiliser Terminal ou [iTerm2](https://www.iterm2.com/).
> Sous Windows, vous pouvez utiliser [Babun](https://babun.github.io/).

Parmi les commandes de base on notera :

- `cd [path/to/move/to]` : __change directory__
- `pwd` : __print working directory__ (si vous êtes perdu…)
- `ls` : __list directory__ (`ls -la`, details + hidden)
- `mkdir [foldername]` : __make directory__
- `touch [path/to/filename]` : crée un fichier
- `echo 'foo' > [path/to/filename]` : crée un fichier contenant 'foo'
- `rm [path/to/filename]` / `rm -r [path/to/foldername]` : efface un fichier / dossier
- `which [command]` : affiche (ou pas) l'emplacement d'une commande
- `[command] -h | --help | …` : aide à l'utilisation de la commande
- `clear` : rafraîchit la fenêtre du terminal
- `exit` : 🚪…

### Note

- `~` (tilde), fait référence à la racine de votre dossier utilisateur
- `/`, fait référence à la racine de votre système
- `.`, fait référence au dossier courant
- `..`, fait référence au dossier parent

> Ressources :
>
> - [Le designer qui chuchotait à l'oreille des chevaux](http://slides.com/thierrymichel/le-designer-qui-chuchotait-l-oreille-des-ordinateurs#/)
> - [Command Line Crash Course](https://learnpythonthehardway.org/book/appendixa.html)

## Environnement JS

### Node.js

> Ressources : [Node.js](https://nodejs.org/en/)

### nvm (Node Version Manager)

Permet de gérer plusieurs versions de Node.js sur un même système.
Simplifie également la question des permissions en s'exécutant et en installant les packages globaux dans le dossier utilisateur…

Installation :

```sh
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.0/install.sh | bash
nvm install node
```

> Ressources : [nvm](https://github.com/creationix/nvm)

### npm

C'est le gestionnaire de "packages" de Node.js, il est installé par défaut avec ce dernier.
Tout (bon) projet souhaitant utiliser `npm` doit être initialisé via `npm init`.

Cette dernière commande crée simplement un fichier `package.json`, sorte de "pedigree/carte d'identité" de votre projet.

Exemple :

```json
{
  "name": "heaj",
  "version": "1.0.0",
  "description": "Développement web avancé - 3e année",
  "main": "README.md",
  "repository": {
    "type": "git",
    "url": "git+https://github.com/thierrymichel/heaj.git"
  },
  "keywords": [
    "heaj",
    "javascript",
    "learning",
    "threejs"
  ],
  "author": "thierrymichel <thmichel@gmail.com> (http://thierrymichel.net)",
  "license": "http://unlicense.org/",
  "bugs": {
    "url": "https://github.com/thierrymichel/heaj/issues"
  },
  "homepage": "https://github.com/thierrymichel/heaj#readme"
}
```

Lorsque vous installez un package, vous pouvez le sauvegarder automatiquement comme dépendance (simple ou de développement).

- Sans sauvegarde : `npm install [package-name]` ou `npm i [package-name]`
- Comme dépendance : `npm i --save [package-name]` ou `npm i -S [package-name]`
- Comme dépendance de dev : `npm i --save-dev [package-name]` ou `npm i -D [package-name]`

De telle sorte que, lorsque vous récupérez un (votre) projet, la commande `npm install` (`npm i`) vous permet d'installer les différents packages nécessaires à ce projet ou/et à son développement !

`npm` vous permet également d'exécuter des scripts "Node.js" via `npm run [script-name]` (voir plus tard).

> Ressources: [npm](https://www.npmjs.com/)

### Git

Ce cours/projet utilise `git`.

`git` vous permet de gérer facilement l'historique et les versions de votre projet.
Lorsque vous apportez des modifications, vous pouvez les associer à un __commit__ lui-même assorti d'un message.
Chaque __commit__, représente un "noeud" de l'arbre historique de votre projet auquel vous pouvez revenir aisément.

Commandes principales :

- `git status`
- `git pull`
- `git add`
- `git commit`
- `git push`

Doit-on tout mettre dans notre dépôt ? Non !
Toutes données à caractère sensible ainsi que, en règle génerale, les fichiers générés automatiquement doivent être exclus.
À cette fin, on utilise un fichier nommé `.gitignore` qui reprend ce qui ne doit pas figurer dans notre "repo".

> Ressources :
>
> - [Petit guide](http://rogerdudler.github.io/git-guide/index.fr.html)
> - [gitignore.io](https://www.gitignore.io/)
> - [Git](https://git-scm.com/)

---

⚠️ Ce projet utilise le système de __tags__ pour identifier ses différentes étapes.

Vous pouvez afficher les tags via `git tag`.
Vous pouvez à tout moment passer à une autre étape grâce à `git checkout [tag-name]`…

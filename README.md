# 🐕 Husky + commitlint + lint-staged

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Next.js](https://img.shields.io/badge/Next.js-15+-black)](https://nextjs.org/)
[![Husky](https://img.shields.io/badge/Husky-9+-purple)](https://typicode.github.io/husky/)

> Guide complet pour automatiser la qualité des commits Git dans vos projets Next.js

## 🎯 Pourquoi ce guide ?

Vous en avez marre des messages de commit comme `"fix truc"` ou `"wip"` ?  
Vous voulez que votre équipe suive une convention propre sans avoir à faire la police ?

Ce guide vous montre comment mettre en place **automatiquement** :

- ✅ Des messages de commit formatés selon [Conventional Commits](https://www.conventionalcommits.org/)
- ✅ Du code automatiquement formaté et linté avant chaque commit
- ✅ Des hooks Git qui bloquent les mauvais commits
- ✅ Une configuration compatible **npm** ET **pnpm**

## 🚀 Démo rapide

```bash
# ❌ Mauvais commit → bloqué
$ git commit -m "fix truc"
⧗   input: fix truc
✖   type may not be empty [type-empty]
husky - commit-msg script failed (code 1)

# ✅ Bon commit → accepté
$ git commit -m "fix(auth): corriger la validation du formulaire"
✔ Commit accepté
```

## 📚 Ce que vous allez apprendre

| Outil | Rôle |
|-------|------|
| **Husky** | Chef d'orchestre – déclenche des scripts sur les événements Git |
| **lint-staged** | Formate et lime UNIQUEMENT les fichiers modifiés |
| **commitlint** | Valide le format des messages de commit |

## 🛠️ Installation rapide

```bash
# Avec npm
npm install --save-dev husky lint-staged @commitlint/cli @commitlint/config-conventional
npx husky init

# Avec pnpm
pnpm add --save-dev husky lint-staged @commitlint/cli @commitlint/config-conventional
pnpm exec husky init
```

> 📖 Le guide complet est disponible dans le fichier `index.html`

## 📁 Structure finale

```
votre-projet/
├── .husky/
│   ├── pre-commit          # lance lint-staged
│   └── commit-msg          # valide le message
├── commitlint.config.js    # règles de validation
└── package.json            # contient "prepare": "husky"
```

## ✍️ Convention des commits

```
type(scope): description courte

# types les plus courants :
feat     → nouvelle fonctionnalité
fix      → correction de bug
docs     → documentation
refactor → réécriture sans changement fonctionnel
chore    → maintenance, dépendances
test     → ajout de tests
perf     → amélioration de performance
```

## 🧪 Tester votre configuration

```bash
# Tester commitlint seul
echo "fix(auth): corriger login" | npx commitlint

# Tester lint-staged seul
npx lint-staged

# Faire un vrai commit
git add .
git commit -m "feat(auth): ajouter connexion Google"
```

## 🌍 Liens utiles

- [Documentation Husky](https://typicode.github.io/husky/)
- [Documentation commitlint](https://commitlint.js.org/)
- [Conventional Commits](https://www.conventionalcommits.org/)

## 📄 Licence

MIT — Libre d'utilisation, modification et partage.

## 🙏 Contribution

Les issues et pull requests sont les bienvenues pour améliorer ce guide !

---

**Fait avec ❤️ pour la communauté Next.js**

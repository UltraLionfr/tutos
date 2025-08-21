# 📘 Bases de Git

Cette section couvre les **fondamentaux de Git** : initialiser un dépôt, gérer les commits et manipuler les branches.

---

## Initialiser un dépôt
Créer un nouveau dépôt Git dans un dossier existant : `git init`

Cloner un dépôt distant existant : `git clone <url>`

---

## Suivi des fichiers

Vérifier l’état des fichiers (suivis, non suivis, modifiés) : `git status`

Ajouter un fichier spécifique : `git add fichier.txt`

Ajouter tous les fichiers modifiés : `git add .`

Valider les changements avec un message clair : `git commit -m "Description de la modification"`

### Format des commits

Pour plus de clarté dans l’historique, j'utilise ces préfixes :

* `feat:` ➝ nouvelle fonctionnalité

  ```bash
  git commit -m "feat: ajout du formulaire de connexion"
  ```
* `fix:` ➝ correction de bug

  ```bash
  git commit -m "fix: correction de l’affichage sur mobile"
  ```
* `chore:` ➝ tâches diverses (config, dépendances, refactor, etc.)

  ```bash
  git commit -m "chore: mise à jour des dépendances"
  ```
* `docs:` ➝ documentation

  ```bash
  git commit -m "docs: ajout de la section installation"
  ```

---

## Gestion des branches

Lister les branches : `git branch`

Créer une nouvelle branche : `git branch exemple`

Basculer sur une branche : `git checkout exemple`

Créer **et** basculer en même temps : `git checkout -b exemple`

Fusionner une branche dans `main` :

```bash
git checkout main
git merge exemple
```

---

## 🔄 Synchronisation avec un dépôt distant

Associer un dépôt distant : `git remote add origin <url>`

Récupérer les dernières modifications : `git pull origin main`

Envoyer les changements locaux : `git push origin main`

---

## 🚀 Utilisation de GitHub CLI (`gh`)

Exemples utiles :

* Cloner un dépôt : `gh repo clone utilisateur/nom-du-depot`

* Créer une pull request : `gh pr create --fill`

* Lister les issues : `gh issue list`

* Ouvrir le dépôt sur GitHub dans le navigateur : `gh repo view --web`

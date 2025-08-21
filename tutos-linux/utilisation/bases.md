# Commandes de base Linux

---

## Navigation dans le système de fichiers

```bash
pwd              # Affiche le chemin courant
ls               # Liste les fichiers
ls -l            # Liste détaillée
ls -a            # Affiche aussi les fichiers cachés
cd /chemin       # Se déplacer dans un dossier
cd ..            # Remonter d’un dossier
cd ~             # Aller dans le home de l’utilisateur
```

---

## Manipulation de fichiers et dossiers

```bash
touch fichier.txt       # Créer un fichier vide
mkdir dossier           # Créer un dossier
cp fichier.txt copie.txt # Copier un fichier
mv fichier.txt /tmp/    # Déplacer ou renommer
rm fichier.txt          # Supprimer un fichier
rm -r dossier/          # Supprimer un dossier et son contenu
```

---

## Lecture de fichiers

```bash
cat fichier.txt         # Afficher le contenu complet
less fichier.txt        # Lecture page par page
head fichier.txt        # 10 premières lignes
tail fichier.txt        # 10 dernières lignes
tail -f fichier.log     # Suivi en temps réel
```

---

## Recherche

```bash
find / -name fichier.txt     # Rechercher un fichier
grep "mot" fichier.txt       # Rechercher du texte dans un fichier
grep -r "mot" /chemin        # Recherche récursive
```

---

## Permissions et propriétaires

```bash
ls -l fichier.txt        # Affiche les permissions
chmod 644 fichier.txt    # Modifier les permissions
chown user:group fichier.txt # Modifier propriétaire et groupe
```

---

## Exécution de commandes utiles

```bash
whoami        # Affiche l’utilisateur courant
uname -a      # Infos système
uptime        # Depuis combien de temps le système tourne
history       # Historique des commandes
clear         # Nettoyer l’écran du terminal
```

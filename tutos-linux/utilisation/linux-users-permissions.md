# Guide Sécurité Linux – Utilisateurs, groupes et permissions

---

## Gestion des utilisateurs

```bash
adduser nom_utilisateur       # Créer un nouvel utilisateur
passwd nom_utilisateur        # Définir ou changer son mot de passe
deluser nom_utilisateur       # Supprimer un utilisateur
id nom_utilisateur            # Afficher l’UID, GID et groupes de l’utilisateur
who                           # Afficher les utilisateurs connectés
```

---

## Gestion des groupes

```bash
groupadd nom_groupe           # Créer un nouveau groupe
adduser user groupe           # Ajouter un utilisateur à un groupe
gpasswd -d user groupe        # Retirer un utilisateur d’un groupe
groups user                   # Afficher les groupes d’un utilisateur
```

---

## Utilisation de sudo

```bash
sudo commande                 # Exécuter une commande en tant qu’administrateur
sudo -i                       # Ouvrir un shell root
visudo                        # Modifier la configuration sudo en sécurité
```

---

## Permissions des fichiers

Les permissions se composent de 3 niveaux : **utilisateur (u)**, **groupe (g)** et **autres (o)**.

```bash
ls -l fichier.txt             # Afficher les permissions
chmod 644 fichier.txt         # Donner rw-r--r-- (lecture/écriture user, lecture groupe/autres)
chmod u+x script.sh           # Ajouter l’exécution pour l’utilisateur
chown user:group fichier.txt  # Changer propriétaire et groupe
```

## Exemple d'ajout utilisateur

Créer un utilisateur, l’ajouter à `sudo` et sécuriser ses permissions :

```bash
adduser toto
usermod -aG sudo toto
chmod 700 /home/toto
```

---

## Droits spéciaux

- **SUID (s)** : exécution avec les droits du propriétaire  
- **SGID (s)** : exécution avec les droits du groupe  
- **Sticky bit (t)** : protège la suppression des fichiers dans un dossier  

```bash
chmod u+s fichier             # Activer SUID
chmod g+s dossier             # Activer SGID
chmod +t /dossier             # Activer sticky bit
```

---

## Sécurité des connexions

```bash
last                          # Voir l’historique des connexions
lastb                         # Connexions échouées (si activé)
whoami                        # Afficher l’utilisateur courant
w                             # Voir les utilisateurs connectés et leurs processus
```

# Guide SSH

---

## Connexion à un serveur

```bash
ssh utilisateur@ip_du_serveur
```

Exemple :

```bash
ssh root@192.168.1.1
```
---

## Utilisation d'une clé SSH

### Génération d'une clé SSH

```bash
ssh-keygen -t ed25519 -C "toto@exemple.com"
```

- `-t ed25519` : type de clé
- `-C` : commentaire pour identifier la clé

Les clés sont générées par défaut dans `~/.ssh/` :
- **Clé privée** : `id_ed25519` (à garder secrète)
- **Clé publique** : `id_ed25519.pub` (à partager avec le serveur)

---

### Copie de la clé sur le serveur

```bash
ssh-copy-id utilisateur@ip_du_serveur
```

Exemple :

```bash
ssh-copy-id root@192.168.1.1
```

---

## Configuration avancée (fichier `~/.ssh/config`)

Création d'un fichier de configuration pour simplifier les connexions :

```bash
nano ~/.ssh/config
```

Exemple de contenu :

```
Host mon-serveur
    HostName 192.168.1.1
    User root
    Port 22
    IdentityFile ~/.ssh/id_ed25519
```

Se connecter :

```bash
ssh mon-serveur
```

---

## Transfert de fichiers

### Avec `scp`

```bash
scp fichier.txt toto@192.168.1.1:/home/toto/
```

---

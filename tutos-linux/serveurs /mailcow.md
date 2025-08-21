# Informations serveur (exemple)

* **Utilisateur**  : `root`
* **Mot de passe** : `supermotdepasse`
* **Adresse IP**   : `192.168.1.10/24`
* **Passerelle**   : `192.168.1.1`

---

# Installation de base

```bash
apt update && apt upgrade -y
apt install sudo curl git -y
```

---

# Installation de Docker

```bash
su
curl -sSL https://get.docker.com/ | CHANNEL=stable sh
systemctl enable --now docker
```

---

# Installation de Docker Compose

```bash
curl -sSL https://github.com/docker/compose/releases/download/v$(curl -Ls https://www.servercow.de/docker-compose/latest)/docker-compose-$(uname -s)-$(uname -m) > /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
```

---

# Désactivation de Postfix (port 25)

```bash
sudo ss -ltnp | grep :25
sudo systemctl stop postfix
sudo systemctl disable postfix
```

---

# Installation de Mailcow

```bash
cd /opt
git clone https://github.com/mailcow/mailcow-dockerized
cd mailcow-dockerized
./generate_config.sh
```

### Réponses recommandées :

* **Hostname (FQDN)** : `mail.exemple.com`
* **Timezone**        : `Europe/Paris`
* **Branch**          : `master` (par défaut)

---

# Lancement du serveur

```bash
docker compose pull
docker compose up -d
```

---

# Vérification du service

```bash
docker compose ps
docker compose logs -f
```

---

# URL de connexion

* **URL** : [https://mail.exemple.com/admin](https://mail.exemple.com/admin)
* **Utilisateur** : `admin`
* **Mot de passe** : `moohoo` (par défaut, à changer après installation)

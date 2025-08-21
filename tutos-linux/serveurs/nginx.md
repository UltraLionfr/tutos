# Guide Nginx

## Installation de Nginx

Sur Debian/Ubuntu :

```bash
sudo apt update
sudo apt install nginx -y
```

Vérifier que le service est actif :

```bash
systemctl status nginx
```

Lancer/activer Nginx au démarrage :

```bash
sudo systemctl enable --now nginx
```

---

## Emplacement des fichiers importants

- **Configuration principale** : `/etc/nginx/nginx.conf`
- **Sites disponibles** : `/etc/nginx/sites-available/`
- **Sites activés** : `/etc/nginx/sites-enabled/`
- **Logs** : `/var/log/nginx/access.log` et `/var/log/nginx/error.log`

---

## Exemple de configuration (site simple)

Créer un fichier dans `/etc/nginx/sites-available/<exemple>.conf` :

```nginx
server {
    listen 80;
    server_name monsite.com www.<exemple>.com;

    root /var/www/<exemple>;
    index index.html;

    location / {
        try_files $uri $uri/ =404;
    }
}
```

Activer le site et recharger Nginx :

```bash
ln -s /etc/nginx/sites-available/<exemple> /etc/nginx/sites-enabled/
sudo nginx -t
sudo systemctl reload nginx
```

---

## Redirection HTTP → HTTPS

```nginx
server {
    listen 80;
    server_name <exemple>.com www.<exemple>.com;
    return 301 https://$host$request_uri;
}
```

---

## Reverse Proxy (ex. pour une app sur port 3000)

```nginx
server {
    listen 80;
    server_name app.<exemple>.com;

    location / {
        proxy_pass http://127.0.0.1:3000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```

---

## Sécuriser avec Certbot (HTTPS)

Installer Certbot :

```bash
sudo apt install certbot python3-certbot-nginx -y
```

Générer un certificat SSL :

```bash
sudo certbot --nginx -d <exemple>.com -d www.<exemple>.com
```

Renouvellement automatique :

```bash
sudo systemctl list-timers | grep certbot
```

---

## Bonnes pratiques

- Toujours tester la configuration avant un reload :

```bash
sudo nginx -t
```

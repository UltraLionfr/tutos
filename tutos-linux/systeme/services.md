# Guide Services & démons

## Commandes principales avec `systemctl`

### Vérifier l’état d’un service

```bash
systemctl status nom_du_service
```

Exemple :

```bash
systemctl status ssh
```

---

### Démarrer / Arrêter / Redémarrer un service

```bash
sudo systemctl start nom_du_service
sudo systemctl stop nom_du_service
sudo systemctl restart nom_du_service
```

---

### Activer / Désactiver au démarrage

```bash
sudo systemctl enable nom_du_service
sudo systemctl disable nom_du_service
```

---

### Recharger la configuration d’un service

```bash
sudo systemctl reload nom_du_service
```

---

## Liste des services actifs

```bash
systemctl list-units --type=service
```

Lister uniquement les services en échec :

```bash
systemctl --failed
```

---

## Logs des services

Les logs passent par **journalctl** :

```bash
journalctl -u nom_du_service
```

Suivre les logs en direct :

```bash
journalctl -u nom_du_service -f
```

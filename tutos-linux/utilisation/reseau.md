# Guide réseau

---

## Vérification de la connectivité

```bash
ping google.com         # Tester la connectivité avec une adresse
ping -c 4 8.8.8.8       # Envoyer seulement 4 paquets
```

---

## Résolution DNS

```bash
nslookup exemple.com    # Interroger un serveur DNS
dig exemple.com         # Obtenir des infos DNS détaillées
host exemple.com        # Résolution simple
```

---

## Téléchargement et requêtes HTTP

```bash
curl http://exemple.com         # Récupérer une page
curl -I http://exemple.com      # Récupérer uniquement les en-têtes HTTP
wget http://exemple.com/fichier # Télécharger un fichier
```

---

## Informations réseau de la machine

```bash
ip a                             # Afficher les interfaces et adresses IP
ip r                             # Afficher la table de routage
hostname -I                      # Afficher les adresses IP locales
hostname -I | awk '{print $1}'   # Afficher uniquement la première adresse IP de la machine
```

---

## Connexions et ports

```bash
ss -ltn   # Lister les ports TCP en écoute
ss -ltnp  # Avec les PID et programmes associés
```

---

## Tests avancés

```bash
traceroute exemple.com   # Afficher le chemin réseau (paquets ICMP)
mtr exemple.com          # Traceroute en continu (si installé)
nc -zv ip port           # Tester si un port est ouvert
```

---

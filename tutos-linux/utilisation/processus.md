# Guide des processus Linux

## Visualiser les processus en cours

```bash
ps aux               # Affiche tous les processus en cours
ps -ef               # Autre format d’affichage
top                  # Vue en temps réel des processus
htop                 # Vue améliorée (si installé)
```

---

## Rechercher un processus

```bash
ps aux | grep nginx        # Rechercher "nginx" dans la liste des processus
pgrep nginx                # Affiche directement les PID correspondants
```

---

## Arrêter un processus

```bash
kill PID                   # Arrêter un processus avec son PID
kill -9 PID                # Forcer l’arrêt (SIGKILL)
pkill nom_du_processus     # Tuer un processus par son nom
```

---

## Priorité des processus

- **nice** : définit la priorité au lancement  
- **renice** : modifie la priorité d’un processus existant  

```bash
nice -n 10 commande        # Lancer avec une priorité réduite
renice -n 5 -p PID         # Modifier la priorité d’un processus
```

---

## Surveillance des ressources

```bash
top                       # Utilisation CPU / RAM
htop                      # Version interactive
uptime                    # Charge moyenne du système
free -h                   # Mémoire disponible
vmstat 2                  # Statistiques système en continu
```

---

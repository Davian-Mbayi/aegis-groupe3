# Documentation Infrastructure & Réseau

## Machine Virtuelle
- **OS :** Debian 12 (Bookworm)
- **Hyperviseur :** VirtualBox
- **Utilisateurs :** `root` (désactivé pour SSH), `aegis` (utilisateur d'audit)

## Configuration Réseau
Conformément aux exigences, la VM dispose de deux interfaces pour isoler les flux :
1. **Interface 1 (NAT) :** Accès Internet pour les mises à jour et installations de paquets.
2. **Interface 2 (Host-Only) :** Réseau privé entre l'hôte et la VM.
   - **IP de la VM :** 192.168.56.10
   - **Usage :** Administration SSH et accès aux services web.

## Services de Sécurité Déployés
- **UFW (Uncomplicated Firewall) :** - Entrée : Port 2222 (SSH) uniquement.
  - Sortie : Autorisé.
- **Fail2ban :** - Prison active sur `sshd`.
  - Bannissement après 3 tentatives infructueuses sur le port 2222.
- **Logging :** Réinstallation de `rsyslog` pour la gestion des fichiers `/var/log/auth.log`.

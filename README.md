# Projet AEGIS - Sécurisation du SI TechSud
**Étudiant :** Adje Kenneth, Souwoye Ibrahim, Davian Mbayi, Divine Merveille
**Formation :** BTC 1 IPSSI 2026

## Présentation
Ce dépôt contient les travaux réalisés dans le cadre du projet AEGIS. L'objectif est d'auditer et de sécuriser l'infrastructure de la PME TechSud suite à une compromission majeure survenue le 18 avril 2026.

## Structure du dépôt
- `infrastructure/` : Documentation de la mise en place du lab.
- `configs/` : Fichiers de configuration sécurisés (SSH, Fail2ban, etc.).
- `tp_complementaire/` : Scripts d'audit, fichiers PHP et outputs (Phase 1, 2 et 3).
- `rapport/` : Rapport d'audit professionnel.

## État d'avancement
- [x] Déploiement VM Debian 12 (VirtualBox)
- [x] Configuration réseau isolée (NAT + Host-Only)
- [x] Durcissement SSH & Pare-feu (UFW)
- [x] Mise en place Fail2ban & Gestion des logs
- [/] Phase 1 : Base de données (En cours)

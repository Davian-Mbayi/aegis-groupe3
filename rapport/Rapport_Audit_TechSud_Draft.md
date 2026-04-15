# Rapport d'Audit de Sécurité - TechSud SAS
**Référence :** TS-2026-SSI-001  
**Date :** Avril 2026  
**Auteur :** Davian Mbayi

## 1. Contexte de l'incident
Le 18 avril 2026, le serveur principal de TechSud a subi une attaque majeure. Les signes détectés incluent :
- [cite_start]Saturation CPU à 98% (processus `kworker/u4:2`)[cite: 127].
- [cite_start]Connexion SSH active depuis un nœud Tor (185.220.101.47)[cite: 128].
- [cite_start]Présence d'un webshell PHP dans `/var/www/html/upload/`[cite: 167].

## 2. Périmètre de l'Audit
L'audit se concentre sur la sécurisation d'un serveur Debian 12 reproduisant les services critiques :
- Accès distant (SSH)
- Base de données (MariaDB)
- Serveur Web (Apache/PHP)

## 3. Mesures de Remédiation Initiales
### 3.1 Durcissement SSH
Le service SSH a été sécurisé pour bloquer les vecteurs d'attaque par brute-force :
- **Port custom :** Changement du port 22 vers 2222.
- **Authentification :** Désactivation des mots de passe au profit de clés asymétriques (ED25519).
- **Accès Root :** Interdiction stricte de connexion en root via SSH.

### 3.2 Défense Périmétrique
Mise en place d'un pare-feu applicatif (UFW) et d'un système de bannissement automatique (Fail2ban) pour protéger le point d'entrée SSH.

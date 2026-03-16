![Security](https://github.com/Crabe19/devsecops-lab/actions/workflows/security.yml/badge.svg)

🔒 DevSecOps Lab - Sécurisation d'une App Node.js

Ce projet a pour but de mettre en place un pipeline CI/CD sécurisé (DevSecOps) pour détecter et corriger les vulnérabilités d'une application Node.js.
🚀 Fonctionnalités du Pipeline

Le workflow GitHub Actions exécute automatiquement les contrôles suivants :

    SAST (Semgrep & CodeQL) : Analyse statique pour détecter les failles de code (injections, mauvaises pratiques).

    SCA (npm audit) : Vérification des vulnérabilités dans les dépendances tierces.

    Secrets Detection (Gitleaks) : Scan de l'historique Git pour empêcher la fuite de clés API ou mots de passe.

    Container Scan (Trivy) : Analyse de l'image Docker pour détecter les failles système (image Alpine utilisée).

🛠️ Installation et Utilisation
Prérequis

    Docker

    Node.js (v22+)

Setup local

    Cloner le repo :
    Bash

    git clone https://github.com/Crabe19/devsecops-lab.git

    Configurer les variables d'environnement (créer un fichier .env basé sur .env.example).

    Lancer l'application avec Docker :
    Bash

    docker build -t secure-app .
    docker run -p 3000:3000 secure-app

📊 Sécurité

Le projet respecte les standards de sécurité suivants :

    Image de base Alpine pour réduire la surface d'attaque.

    Utilisateur non-root pour l'exécution du conteneur.

    Gestion des secrets via GitHub Secrets et variables d'environnement.

    Protection contre les injections et Rate Limiting implémentés.
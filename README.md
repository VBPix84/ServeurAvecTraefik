# Serveur Avec Traefik

Reflexion projet pour mon serveur en utilisant traefik

# Objectifs

1. Supporter ma domotique
2. Sauvegarder (mariadb) des données des capteurs domotiques)
3. Supporter un serveur Web NginX pour le stockage de documents accessible pour les services installés sur le serveur (ex: bibliothèques de tts en mp3 pour l'alarme)
4. Supporter des serveurs de dev de sites web (Un docker-compose avec NginX, Mariadb et Php par site web)
5. Stocker ma base de donnée de mot de passes bitwarden
6. Pouvoir accéder à des services depuis l'extérieur en toute sécurité (reverse proxy)

Le serveur est sur une base Linux Debian et tout est installé en container docker (avec docker-compose).

## Organisation de ma domotique

- [x] #739


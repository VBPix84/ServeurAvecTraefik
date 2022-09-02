# Serveur Avec Traefik

Reflexion projet pour mon serveur en utilisant traefik

# Objectifs

1. Supporter ma domotique
2. Sauvegarder (mariadb) des données des capteurs domotiques)
3. Supporter un serveur Web NginX pour le stockage de documents accessible pour les services installés sur le serveur (ex: bibliothèques de tts en mp3 pour l'alarme)
4. Supporter des serveurs de dev de sites web (Un docker-compose avec NginX, Mariadb et Php par site web)
5. Stocker ma base de donnée de mot de passes bitwarden
6. Pouvoir accéder à des services depuis l'extérieur en toute sécurité (reverse proxy)

Le serveur est sur une base Linux Debian et *tout est installé en containers docker* (avec docker-compose).

## Organisation de ma domotique

J'utilise principalement Zigbee2mqtt et NodeRed. HA me sert uniquement de DashBoard

Liste des containers :
- NodeRed
- Zigbee2mqtt
- Home Assistant
- Mosquitto
- Mqtt-explorer (stack mqtt-explorer)

Ce qui est fait actuellement :
- [X] Capteurs Zigbee appairés avec Zigbee2mqtt
- [X] Zigbee2mqtt publie vers Mosquitto
- [X] Home Assistant récupère des infos depuis MQTT
- [X] Home Assistant me sert de dashboard
- [X] NodeRed récupère des infos de Z2M (en direct), via MQTT ou via HA.
- [X] NodeRed diffuse des fichiers mp3 dans les enceintes de la maisons via une palette Cast.
- [X] NodeRed envoie des notifications via un bot telegram
- [X] NodeRed recoit des infos depuis des conversations telegram grâce au bot

Ce qui n'est pas fait actuellement :
- [ ] Sauvegarde des données des capteurs (températures par ex)
- [ ] Accéder au dashboard HA de l'extérieur
- [ ] Accéder à NR de l'extérieur ?

Actuellement, les containers sont dans un docker-compose en stack "vincent" - je ne sais pas pourquoi - et network: domotique (cf docker-compose_domotique.yaml)
Les ports sont précisés dans le docker-compose

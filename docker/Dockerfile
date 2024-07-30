# sudo docker build ./ -t ovitrine:v1 : Build l'image pour le projet ovitrine
# sudo docker run -d -p 8080:3000 ovitrine:v1 : Créer le conteneur à partir de l'image buid précédemment
# -d = mettre le processus en arrière plan, -p = bind le port host:container

# FROM pour dire à Docker quelle image utilisé
FROM node:20-slim

# RUN pour éxecuter des commandes dans le conteneur
RUN mkdir app

# WORKDIR pour changer de dossier de travail
WORKDIR /app

# COPY pour copier l'ensemble des dossiers / fichiers de l'application
# Premier "./" qui défini le dossier de la machine hôte, second "./" le dossier du conteneur
COPY ./ ./

# Installation des dépendances npm
RUN npm install

# EXPOSE pour rendre un port accessible à l'extérieur du conteneur
EXPOSE 3000

# CMD pour définir une commande lors du démarrage du conteneur
CMD npx ts-node server.ts
# commandes :
voir liste images : 
sudo docker image ls
sudo docker run --help
sudo docker ps (voir les conteneur actifs)
sudo docker ps -a (tous meme ceux eteint)
sudo docker log
sudo doxker kill arrete conteneur et supprime
tt supprimer(conteneurs, images, ntework) , sudo docker system prune
# conteniriser un challenge
1. ouvre le challenge (ex s01_o-vitine) avant npm run start ds implementation ou npx ts-node server.ts
npm run start lance sur la machinie, moi je veux crééer un conteneur avec tt le code de l'application et disponible à l'extérieur

## les étapes 
creation d'image, build l'image, créer un conteneur, quand on le créé, on va devoir binder le port
### dockerfile
2. je vais cd implementation
3. créer une docker file : Dockerfile (pas d'extension)
s'appuie d'une image du dockerhub : from => depuis ou on créé l'image, depuis qu'elle image on part
pour aller chercher la version, on va la chercher sur le dockerhub (site). et chercher node js et aller dans tags et voir ce qui est proposés
4. on va run des actions avec run ex créer un dossier app ds le conteneur : RUN mkdir app
5. on lui définit dans quel dossier on va travailler working directory : WORKDIR /app chg dossier de travail
6. un conteneur va avoir l'ensemble du code de l'application, on va copy ds dossier app du contener
# COPY pour copier l'ensemble des dossiers / fichiers de l'application
# Premier "./" qui défini le dossier de la machine hôte, second "./" le dossier du conteneur
COPY ./ ./
copy dossier courant, on est déja ds workdir donc ./
7. install dep RUN npm install (node js est déjà installé car on part d'une image node et y a déjà npm)
8. EXPOSE pour rendre un port accessible à l'extérieur du conteneur
EXPOSE 3000
9. une commande qui va permettre de lancé l'application automatiquement npx td-node server.ts (entrypoint existe aussi)

### build l'image
ds terminale => sudo docker build -h (voir commandes)
sudo docker build ./ -t ovitrine:v1
                chemin du dockerfile -t lui mettre un nom et un tag (v1)
va faire tt instructions du dockerfile
si modif image, rebuild

### creer le conteneur
sudo docker run -d -p 80:3000 ovitrine:v1
sudo docker run -p 80:3000 ovitrine:v1
- detacher => tourne en arrière plan
-p mon port 3000
3000 port du conteneur
nom image
si erreur on supprime sudo docker ps -a 
sudo docker rm suspicious
sudo docker ps -a (plus le docker)

### js son server creer une petite api
voir sur npm (simule un backend en focntion d'un fichier json)
install en global
npm -i json -server
run npm install -g json-server voir dockerfile 2 voir intro docker

### docker front et back
voir s03 local express, docker-compose.yml

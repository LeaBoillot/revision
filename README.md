# revision
ci intégration continue
cd deploiement continue (automatique), une fois que la ci est terminée
grâce au github actions, on peut faire cela (gitlab ci, vercel)
on va utiliser surge

1. nouveau projet, avec vite : npm create vite@latest
2. creer un fichier deploy-github-pages à la racine
3. modifier le vite config .ts
4. github page select branch

## conflits de deux run 
eviter que deux run s'execute en même temps, ex si j'ai push sur la branch main, et que qqn d'autres push en même temps, peut générer des conflits, pour éviter cela, on ajoute le parametre concurrency. On va pouvoir annuler un des deux, si je push, lance l'action et qqn d'autres push sur le même branch, la première que j'ai fait avant mon collègue s'annule et prend en compte le push le plus tardif, comme ça pas de conflit entre les diff run d'actions
```yml
# Autorise un seul déploiement à la fois
concurrency:
  group: "github-pages"
  cancel-in-progress: true
```
1. installation de surge npm i --global surge, installé en global
2. surge dans terminal (demande de se connecter) 
3. lui donner le dist => /home/student/s123revisions/vite-project/dist
4. domaine créer un domaine ex react-geri-lea.surge.sh

------
1. surge yml
2. ajouter workflow dispatch pour mettre en production manuellement 'ajoute couche de sécur


Installation CLI (Command Line Interface) :

Pre-requis :
- Creer projet ;
- Dans le projet, creer dossiers public/index.html + src/style.css

1 - Commandes :
Executer : npm init -y
Executer : npm install -D tailwindcss
Executer : npx tailwindcss init <- pour creer tailwind.config.js  
Dans tailwind.config.js :   content: ["./public/*.{html, css}", "./src/*.css", "./public/img/*.{jpg, png}", "./public/*.js"] <= ecouter les fichiers suivants

2 - Dans src/style.css, ajouter : 
@tailwind base; - @tailwind = @import du module de base de tailwind
@tailwind components; - @tailwind = @import du module de composants de tailwind
@tailwind utilities; - @tailwind = @import du module d'utilitaires de tailwind

@layer base - customiser le css du module de base
@layer components - customiser le css du module de composants

Dans package.json/scripts, ajouter : "build-css": "tailwindcss -i ./src/style.css -o ./public/style.css --watch"
Executer : npx build-css / npm run build-css ;
Le dossier public/style.css sera cree avec le contenu complet du style.css de Tailwind et les modifications seront appliques en temps reel

NB : 
Pour activer le live server : 
- l'installer en executant : sudo npm install live-server -g
Mettre le mdp de sa machine
- executer : live-server public <- dossier dans lequel se trouve l'index.html
- copier le lien genere et l'ouvrir dans le navigateur

Apres avoir effectue des modifications dans le tailwind.config.js, toujours arreter le watch (ctrl + c) 
et le relancer (npm run build-css)

Pour changer de police : 
 - aller sur google fonts + chercher la police appropriee
 - copier le link du font et le coller dans le head du index.html
 - dans le tailwind.config.js : dans l'extend : 
 fontFamily : {
        nomchoisi : 'Ubuntu, sans-serif' <- copier le css rule du font concerne de google font
      },  
 - dans le index.html : ecrire dans la classe du body font-nomchoisi

 ****RESPONSIVE****
 sm : mobile <- prendre l'habitude de les mettre a la fin des classes
 md : tablette
 lg : laptop
 xl : desktop

  ****GIT****
  Creer fichier .gitignore et y mettre 'node_modules' <- fichier a ignorer lors du push

  Ctrl + C

  - git init
  - git add .
  - git commit -m 'Message du commit'
  - 
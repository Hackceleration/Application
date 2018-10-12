# Cordova | Vue.js


## Initialisation du projet

Prerequis :
- JDK 1.8 
- Android SDK 
- Sdk tools 

Instalation cordova  : 

    sudo npm install -g cordova

Creation d'un projet cordova : 

    cordova create <Nome de l'app' com>.<NomDeL'Auteur>.<Nome de l'app>

Initialisation Vue.js, rester à la racine du dossier 

     vue init webpack <Nom de l'app>
    
normalement ce message apparaît : 

    ? Target directory exists. Continue? 

faire Yes


    ? Target directory exists. Continue? Yes
    ? Project name 'Nome de l'app'
    ? Project description A Vue.js project
    ? Author Yztoc
    ? Vue build standalone
    ? Install vue-router? Yes
    ? Use ESLint to lint your code? Yes
    ? Pick an ESLint preset Standard
    ? Set up unit tests Yes
    ? Pick a test runner jest
    ? Setup e2e tests with Nightwatch? Yes
    ? Should we run `npm install` for you after the project has been created? (recommended
    ) npm
Supprimer le contenu du dossier www :

    sudo rm -r www/*

Editer le fichier de config index.js : 

    sudo nano ./config/index.js
Rajouter dist apres www : 

    build: {  
        // Template for index.html  
        index: path.resolve(__dirname, '../www/dist/index.html'),
    
        // Paths  
        assetsRoot: path.resolve(__dirname, '../www/dist'),  
        assetsSubDirectory: 'static',  
        assetsPublicPath: '',  
    }
Editer le fichier de config.html : 

    sudo nano ./config.xml
Rajouter dist de même 

    <content src=”dist/index.html” />
Lancer la build (ajout des fichier dans www)

    npm run build
Add platform 

	cordova add platform android 


Lancer une build de l'application (création de l'apk)

    cordova build

Lancer l'application sur l'emulateur 

    cordova run android 
    
Lancer l'application sur un téléphone (installer adb fastboot) au paravant et mettre son téléphone en debugage (paramètre developpeur,  taper 3/4 fois sur le numéro de build du noyeau pour deverouiller le paramètre dev)

	sudo apt-get install adb 
    cordova run android --device

Si il y a une erreur dans la build ou dans le lancement de l'application : affiche les erreurs à corriger 

    cordova requirements 
    
Instalation OnsenUI se mettre à la racine du dossier : 

	npm install onsenui vue-onsenui

Une fois l'installation effectué ajouter ./src/main.js: 

	// Webpack CSS import
	import 'onsenui/css/onsenui.css';
	import 'onsenui/css/onsen-css-components.css';

	import VueOnsen from 'vue-onsenui'; // This imports 'onsenui', so no need to import it separately

	Vue.use(VueOnsen); // VueOnsen set here as plugin to VUE. Done automatically if a call to window.Vue exists in the startup code.
	
On peut maintenant utiliser le framework OnsenUI ajouter cette partie à votre HelloWorld.vue : 
	
	<template id="main-page">
	  <v-ons-page>
	    <v-ons-toolbar>
	      <div class="center">Title</div>
	    </v-ons-toolbar>

	    <p style="text-align: center">
	      <v-ons-button @click="$ons.notification.alert('Hello World!')">
		Click me!
	      </v-ons-button>
	    </p>
	  </v-ons-page>
	</template>




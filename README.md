# Projet 6

## Procédure  d'installation Pour le Projet 6

Installer **CLi Angular**, pour pouvoir faire tourner le serveur de développement sur lequel sera exécuté le code du front-end. 
`npm install -g @angular/cli`

A partir du frontend cloner : `git clone https://github.com/OpenClassrooms-Student-Center/dwj-projet6.git frontend`

Ensuite faire :

`cd frontend` =>
`npm install` si besoin faire : `npm audit fix` =>  
`ng serve`

Acceder à http://localhost:4200

Initialiser **Package.json** qui va lister tous les packages que l'on va utiliser pour ce projet
`cd backend` =>
`npm init`

Creation du **git init** pour le versionning
`cd backend` =>
`git init`

Creation de **.gitignore** pour permetre au repos git les fichier qu'il doit ignorer 

Installation de **nodemon** qui remplace node server, il surveillera les modifications de vos fichiers et redémarrera le serveur lorsqu'il aura besoin d'être mis à jour
`cd backend` =>
`npm install -g nodemon` =>
`nodemon server`

Installation de **express** frameworks de node js
`cd backend` =>
`npm install --save express`

Installation de **body parser** pour extraire l'objet json des demande des requetes
`cd backend` =>  
`npm install --save body-parser`  
`Exemple d'utilisation: const bodyParser = require('body-parser');`

** Connectez votre API à votre cluster MongoDB

Installation de **mongoose** qui facilite les interactions avec notre base de données MongoDB grâce à des fonctions extrêmement utiles.
`cd backend` =>  
`npm install --save mongoose`  
`Exemple d'utilisation: const mongoose = require('mongoose');`


Pour s'assurer que deux utilisateurs ne peuvent pas utiliser la même adresse e-mail, nous utiliserons le mot clé unique pour l'attribut email du schéma d'utilisateur userSchema
`npm install --save mongoose-unique-validator`


Installation de **bcryt** qui est un package de chiffrement pour la fonction signup
`npm install --save bcrypt`

Les tokens d'authentification permettent aux utilisateurs de ne se connecter qu'une seule fois à leur compte. Au moment de se connecter, ils recevront leur token et le renverront automatiquement à chaque requête par la suite. Ceci permettra au back-end de vérifier que la requête est authentifiée.
Installation du package **jsonwebtoken** pour pouvoir créer et vérifier les tokens d'authentification
`npm install --save jsonwebtoken`  
`Exemple d'utilisation: const jwt = require('jsonwebtoken');`

Installation de **multer** pour implémenter des téléchargements de fichiers. 
`npm install --save multer`

Installation de **helmet** qui va proteger l'api de certaines vulnerabilites bien connus du Web en configurant de manière appropriée des en-têtes HTTP :

- csp définit l’en-tête Content-Security-Policy pour la protection contre les attaques de type cross-site scripting et autres injections intersites.  
- hidePoweredBy supprime l’en-tête X-Powered-By.
hsts définit l’en-tête Strict-Transport-Security qui imposer des connexions (HTTP sur SSL/TLS) sécurisées au serveur.  
- ieNoOpen définit X-Download-Options pour IE8+.
noCache définit des en-têtes Cache-Control et Pragma pour désactiver la mise en cache côté client.  
- noSniff définit X-Content-Type-Options pour protéger les navigateurs du reniflage du code MIME d’une réponse à partir du type de contenu déclaré.  
- frameguard définit l’en-tête X-Frame-Options pour fournir une protection clickjacking.
xssFilter définit X-XSS-Protection afin d’activer le filtre de script intersites (XSS) dans les navigateurs Web les plus récents.  
`npm install --save helmet`  

Installation de **cors** sert à alléger la sécurité en autorisant les requêtes vers d’autres domaines. C’est pourquoi il est important de bien savoir le configurer pour ne pas autoriser tout et n’importe quoi.
C’est le site qui indique si le navigateur a le droit ou pas d’échanger avec lui via l’entête Access-Control-Allow-Origin. Il existe un ensemble d’entêtes pour configurer plus finement les échanges avec le navigateur.
`npm install cors --save`

Installation de **dotenv** pour separer les id et password du mongoDb de app.js pour des questions de securité  
Ce fichier ne doit pas être versionné, il faut donc l’ajouter à .gitignore.  
`npm install dotenv`  

Installation de **express-session** qui va stocker les donees du session sur le server. il ne sauvegarde que l’ID session dans le cookie lui-même, mais pas les données de session. Par défaut, il utilise le stockage en mémoire et n’est pas conçu pour un environnement de production.  
`npm install --save express-session`


# Code HTTP

## https://developer.mozilla.org/fr/docs/Web/HTTP/Status


## Découvrez le CRUD

Le CRUD est la liste des actions de bases que vous pouvez effectuer sur une ressource. C’est un acronyme qui signifie Create (créer), Read (lire), Update (mettre à jour), et Delete (supprimer). Bien que le CRUD ne constitue pas vraiment un mécanisme technique en soi, chaque action CRUD est associée à un verbe HTTP. Voici la cartographie :
https://openclassrooms.com/fr/courses/6573181-adoptez-les-api-rest-pour-vos-projets-web/6818386-realisez-vos-premieres-requetes-sur-une-api#/id/r-6818393

Action CRUD            Verbe HTTP associé
Create (Créer)         POST (Publier)
Read (Lire)            GET (Obtenir)
Update (Mettre à jour) PUT (Mettre)
Delete (Supprimer)     DELETE (Supprimer)

GET est le verbe HTTP pour obtenir des données, et il est généralement utilisé avec un ID pour obtenir une donnée spécifique.
Utilisez Postman pour tester les API.

La documentation est le manuel d’utilisation d’une API.
La documentation vous permet de trouver la liste des endpoints accompagnée du verbe HTTP correspondant.

## Token

Un token est généralement une chaîne longue et unique de lettres et de chiffres aléatoires que l’on assigne à un utilisateur. Le token est un peu comme un numéro de passeport : il est unique et permet de vous identifier. L’API peut donc l’utiliser pour savoir qui effectue la requête, et surtout de quel niveau d’autorisation cette personne dispose.


# Partie Securité

La confidentialité. C'est l'assurance que les personnes non autorisées n'accèdent pas à des informations sensibles.

L'intégrité. Elle permet d'être sûr que les données sont fiables et n'ont pas été modifiées par des personnes non autorisées.

La disponibilité. C'est l’assurance qu'il n'y a pas de perturbation d'un service ou de l'accessibilité aux données.

L’OWASP est une organisation à but non lucratif qui propose des référentiels sur les risques de sécurité des applications web. Le Top Ten 2017 de l'OWASP est la dernière mise à jour sur les risques de sécurité des applications web aujourd'hui.


**Découvrez la norme PCI DSS**
La norme Payment Card Industry Data Security Standard (PCI DSS) est une norme établie pour toutes les entreprises qui traitent des données bancaires. La sécurisation des données bancaires met l'accent sur la sécurité lors de la transmission, du traitement et du stockage des données. 


### Top Ten de l’OWASP

**1 - Injection**
Une attaque par injection est une attaque permettant l’injection de code arbitraire dans l’application. Cela se produit lorsque des données non maîtrisées sont exécutées par le moteur présent sur le backend de l’application. Les données de l’attaquant sont exécutées sans autorisations adéquates.

L’injection de code non autorisée peut permettre à un attaquant d’accéder à des données auxquelles il n’a normalement pas accès.

**2 - Piratage de session**
Beaucoup d'applications exigent qu'un utilisateur se connecte pour arriver sur des pages auxquelles lui seul a accès. L’application est vulnérable à une attaque si un utilisateur malveillant peut obtenir un accès non autorisé aux mots de passe, clés et jetons pour pirater la session d'un autre utilisateur.

**3 - Exposition de données sensibles**
Les données stockées ou échangées via une application doivent être protégées pour éviter l’interception par une personne malveillante. Les bases de données qui enregistrent les données personnelles, les données de cartes de crédit, les noms d'utilisateur et les mots de passe représentent une cible de choix pour un pirate. Si ces données ne sont pas chiffrées, elles ne sont pas sécurisées et peuvent être récupérées lorsqu’elles sont en transit par exemple. L'utilisation de techniques de chiffrement et de pratiques de sécurité peut atténuer ce type d’attaques.

**4 - Entités externes XML (XXE)**
Le format XML permet de faciliter l’échange de données sous forme d'arborescence. Il est largement utilisé sur Internet. Il peut être exploité via l’injection XXE ou XML External Entity. XML External Entity est une attaque contre les applications qui parsent des entrées XML (exemple flux RSS). Cette attaque a lieu lorsque l'analyseur XML est mal configuré et contient une référence à une entité externe.

**5 - Contournement du contrôle d’accès.**
Cette attaque vise les fonctionnalités des applications web qui nécessitent un contrôle d'accès. Dans ce cas, les pirates peuvent utiliser l'URL pour contourner l'authentification, par exemple. Ce type d’exploitation peut par exemple révéler comment une base de données est organisée.

**6 - Security Misconfiguration**
Une mauvaise configuration de sécurité est le plus souvent observée dans les en-têtes HTTP qui permettent de donner des indications sur la configuration du serveur, ou via la gestion des exceptions par défaut. Les codes d'erreur et les exceptions courantes peuvent donner à un attaquant un aperçu de l'application.

**7 - Cross-Site Scripting  (XSS)**
Les failles XSS se produisent chaque fois qu'une application inclut des données non fiables dans une nouvelle page web sans validation ou échappement. Les failles XSS permettent aux attaquants d'exécuter des scripts dans le navigateur de la victime, ce qui peut détourner des sessions utilisateur, altérer des sites web ou rediriger l'utilisateur vers un site malveillant.

**8 - Désérialisation non sécurisée (Insecure Deserialisation)**
Une vulnérabilité de type “insecure deserialisation” permet à un utilisateur malveillant d'accéder et de modifier les fonctionnalités de l’application ciblée.

**9 - Utilisation de composants présentant des vulnérabilités connues**
Même si votre application est sécurisée, vous devez vous assurer que le framework, les bibliothèques, les appels API et la plateforme que vous utilisez ne sont pas vulnérables.

Lorsqu'une nouvelle vulnérabilité est découverte, un correctif est généralement proposé. Il faudra alors l’appliquer pour garantir la sécurité de l’application.

**10 - Manque de surveillance et de monitoring**
Pour garantir la sécurité d’une application, il est nécessaire de surveiller et de monitorer les connexions. De nombreux serveurs vulnérables servent de rebond aux attaquants. La mise en place de monitoring permettra de détecter une anomalie sur le serveur.

## Securisation

**Validation des entrees**
La validation des entrées est une excellente pratique en tant que développeur web. Elle limite ce que l'utilisateur peut mettre dans la zone de texte.

Le **hachage** permet de générerune empreinte unique pour une entrée. Le problème est qu’il est possible d’utiliser des rainbow tables, c’est-à-dire des listes de hash préalablement calculés, puis de les utiliser avec une attaque de force brute. Pour éviter ce genre d’attaque, il est possible d’ajouter un sel permettant d’ajouter une donnée supplémentaire, et ainsi renforcer la sécurité.

Le **salage** est une méthode permettant de renforcer la sécurité des informations qui sont destinées à être hachées (par exemple des mots de passe) en y ajoutant une donnée supplémentaire afin d’empêcher que deux informations identiques conduisent à la même empreinte (au même hash). Le but du salage est de lutter contre les attaques par analyse fréquentielle (permettant l’analyse des fréquences des caractères employés), les attaques utilisant des rainbow tables, les attaques par dictionnaire et les attaques par force brute.

## Mettez en place le HTTPS

Pour créer un serveur web pour votre application web, Node.js est une plateforme populaire. Cependant, il utilise HTTP par défaut pour la transmission de données. 

Pour utiliser HTTPS, Il suffit de spécifier l'utilisation du module HTTPS sur Node.js.

Pour démarrer un serveur HTTP sur Node.js, le code est le suivant :


`var https = require('https');
http.createServer(function (req, res) {
}).listen(8080);`

Obtenir un certificat SSL pour notre serveur

## Cross-Origin Resource Sharing (CORS).

Le cross-site request forgery (CSRF) est un type de vulnérabilité des services d'authentification web. L’objet de cette attaque est de transmettre à un utilisateur authentifié une requête HTTP falsifiée qui pointe sur une action interne au site, afin qu'il l'exécute sans en avoir conscience et en utilisant ses propres droits.

 - Voici quelques recommandations pour protéger vos données en transit :

N'utilisez GET que pour récupérer des informations.
Utilisez POST pour les informations qui seront manipulées.
Toutes les requêtes POST doivent utiliser HTTPS/SSL pour s'assurer que le corps est chiffré.
Vérifiez tous les modules tiers que vous utilisez pour créer des requêtes GET/POST et utilisez HTTPS pour chacun d'entre eux !


En résumé
Utilisez le HTTPS pour l'ensemble de votre site, même s'il ne contient pas de données sensibles.
Utilisez les requêtes GET pour récupérer les informations et POST pour modifier les informations.
Sécurisez vos cookies pour qu'ils soient transmis par l'en-tête et via HTTPS.
Sécurisez vos sessions en ajoutant une date d'expiration, en sécurisant l'ID et en ne mettant pas cet ID dans l'URL.
L'utilisation du chiffrement dans la couche Transport peut prévenir les attaques MITM !

# Argon5 est un des algorithmes de hachage les plus puissants et fortement recommandés par l'OWASP.

Mongo Mask

cd frontend  
`npm install node-sass@4.14.1`  
ne pas faire npm audit fix  


Questions mentor :

- Script pour lancer les npm a l'ouverture du dossier via vscode
- Comment test notre securiter en localhost ? 
- Faut bien faire 2 user : 1 admin et un user c ca ? 
- Pourquoi dans model on est obliger de mettre default:0

# Securisation Backend

## mis en Place

helmet : ok  
https://connect.ed-diamond.com/MISC/MISC-101/  Vos-entetes-HTTPS-avec-HELMET  

cors : ok  
https://connect.ed-diamond.com/MISC/MISC-101/  Vos-entetes-HTTPS-avec-HELMET  

.Dotenv: ok  
https://www.youtube.com/watch?v=x-SdEjcRPEw&ab_channel=yoursTRULY  
https://dev.to/aritik/connecting-to-mongodb-using-mongoose-3akh  

express-session: ok  set-cookie=> ok
https://www.npmjs.com/package/express-session  
https://github.com/expressjs/session  



 ## RAF 
**npm audit fix** pour fix les vulnerabilités.

**Like** : 
https://docs.mongodb.com/manual/reference/operator/update/
'http://localhost:3000/api/sauces/' + id + '/like',
post( 'http://localhost:3000/api/sauces/:id/like');
likeSauce
default: [] faut enregistrez/delete l'idUser dans un tableau
update + rajout likes de 1 

Securité : 
C
http://expressjs.com/fr/advanced/best-practice-security.html
https://stackoverflow.com/questions/52456065/how-to-format-and-validate-email-node-js
https://www.hackinprovence.fr/comment-securiser-votre-backend-nodejs/
https://geekflare.com/how-to-secure-nodejs/

npm install hpp --save
https://www.freecodecamp.org/news/express-js-security-tips/


express session
https://www.tutorialspoint.com/expressjs/expressjs_sessions.htm
https://www.npmjs.com/package/express-session
https://expressjs.com/fr/advanced/best-practice-security.html

Express Validator
https://flaviocopes.com/express-validate-input/

password validator
https://www.npmjs.com/package/password-validator

email validator
https://www.npmjs.com/package/email-validator

express bouncer
https://www.npmjs.com/package/express-bouncer



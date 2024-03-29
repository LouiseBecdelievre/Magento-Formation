# Formation Magento

## Conseil et info

- Priviligier linux. Magento limité sur Windows et Mac
- Il existe deux versions Communautaire ou Enterprise
- A partir M2.1, fuir Object Manager
- Faire attention aux prérequis. Rester version PHP7.2 pour compatibilité Magento2.3 car présence MCrypt
- Magento par defaut en "default", à passer en "developer", et à passer en prod "production"
	- il faut penser à recompiler
- Nécessiter de recompiler (php bin/magento setup:di:compile) lorsque
	- l'on modifie un construct
	- on modifie un fichier di
- Gérer le cache. Soit le vider régulièrement (php bin/magento cache:flush), soit le désactiver en ligne de commande ou vue admin
- Il est possible de vérifier l'intégrité d'un projet mgento à l'aide du "Security Center" (Nom à vérifier)
- Gestion des roles => Déclaration de ressources => fichier acl.xml
- Magento prefix des bases possible
- Retrouver la config dans la table "core_config_data" (stores config)
- Il faut sauver régulièrement la base (plusieurs fois par jour)
- Utiliser des modules
	- La recherche de Magento de base est un peu limité ( module à  200 / 300 dollars )
	- Review user est basique 
	- Reporting n'est pas très bon et n'aide pas à la comptabilité et statistique
- ? Reflexion : Adobe risque de ne pas conserver la version communautaire
- Possibilité de 
	- Multi vue = multi langue
	- Multi boutique
	- 1 seule instance magento mais multi stat (passer le commentaire runcode) et une seule connexion à l'ERP
- Les autres plus de Magento de base
	- multistock
	- taxes => gestion des monnaies
	- produit / type de produit
	- livraison
- Importance d'activer les crons pour par ex voir apparaitre un produit dans une categorie
	- Un message d'alerte est présent dans l'administration
- Dossier web/generated risque sur les droits dossier generated permission denied => possibilité de supprimer le dossier
- On retrouve les images dans web/pub/media, possiblité de changer les differents tailles de resize par le etc/view.xml
- web/pub/static regroupe le js/css statique mais module/view/frontend/web regroupe les fichiers des layouts
- web/pub/media/import => import d'images, resize automatique des images
- On retrouve les erreurs dans web/pub/errors
- On retrouve l'install de magento dans web/setup
- On peut supprimer le cache par ligne de commande (php bin/magento cache:flush) ou supprimer le dossier web/var/cache
- On retrouve les logs dans web/var/log
- On met le code dans web/app/code
	- copier le registration.php
	- copier etc/module.xml
	- Executer la commande php bin/magento module:enable NOM_NOMMODULE
- Le routing se déclare dans les modules par le fichier etc/frontend/routes.xml 
	- L'id est soit standard (frontend) soit admin (backend)
- Logique "une action = un fichier"
- Insertion de vidéo => vimeo ou youtube, sinon via code attribue text 
- Suggestion de produit possible via l'usage de règles. automatic related product = extension payante
- Dans swagger, génération de l'api key par integrationAdminTokenServiceV1 Interface providing token generation for Admins, saisir ses paramèttres
- Dans l'admin Table>Section>Group>Field
- Prendre des exemples dans le core magento, module contact ou catalog par exemple
- Ressources web js css images dans module/view/web ou projet/lib
- web/app/design/frontend/nommodule
- La surcharge se fait soit par plugin, soit par preference
- Présence du dispatcher symfony : modèle observer

## Les tutos
https://www.pierrefay.fr/formation-magento2.html
https://www.mageplaza.com/magento-2-module-development/
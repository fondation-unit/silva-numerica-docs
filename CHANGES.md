Changes
===

### 10/06/2024

Changements de l'URL d'authentification du device flow :

- retrait de [OAUTH_URL] au profit de [API_URL]
  - l'URL d'interrogation de l'API et l'URL d'authentification sont à présent la même

Ajout de endpoints dans l'API de l'utilisateur :

- route `me` (informations de l'utilisateur lié au token)
- route `user files` (liste des fichiers de l'utilisateur)
- route `post user file` (envoyer un fichier utilisateur)
- route `show user file` (accéder à l'URL d'un fichier utilisateur à partir de son ID)

Voir [https://fondation-unit.github.io/silva-numerica-docs/docs/api/user](https://fondation-unit.github.io/silva-numerica-docs/docs/api/user)

### 11/04/2024

Changements dans la sérialisation des données de l'API des cartes :

- route `index` (liste des cartes) 
  - ajout du type de carte (ex : `"type": "flore"`)
- route `show` (objet carte)
  - ajout du type de carte
  - réorganisation des données selon la fiche des attendus

Voir [https://fondation-unit.github.io/silva-numerica-docs/docs/api/card](https://fondation-unit.github.io/silva-numerica-docs/docs/api/card)

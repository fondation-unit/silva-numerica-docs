---
sidebar_position: 1
---

# Utilisateur

## Me

Récupérer les informations d'un utilisateur.

|Requête|Chemin|Headers|Valeur|
|-------|------|-------|------|
|GET|`/api/v1/me`|`Authorization`|`Bearer [REDACTED]`


## User files

Récupérer la liste des fichiers d'un utilisateur.

|Requête|Chemin|Headers|Valeur|
|-------|------|-------|------|
|GET|`/api/v1/users/user_files`|`Authorization`|`Bearer [REDACTED]`


## User file upload

Envoyer un fichier utilisateur.

|Requête|Chemin|Headers|Valeur|Enctype|Paramètres/Body|
|-------|------|-------|------|-------|---------------|
|POST|`/api/v1/users/user_files/upload`|`Authorization`|`Bearer [REDACTED]`|multipart/form-data|`file`, `nature`, `scenario_id`|

Le paramètre `nature` (str) accepte 2 valeurs : `auto` pour `manual`.

- `auto` désigne les sauvegardes automatiques
- `manual` désigne les sauvegardes manuelles

Le quota de sauvegardes de l'utilisateur s'applique aux 2 natures individuellement. Par exemple, un quota de 5 sauvegardes pour les utilisateurs permettre à l'utilisateur X d'avoir 5 sauvegardes auto et 5 sauvegardes manuelles.

:::note

Le nombre de fichiers qu'un utilisateur peut posséder dépend du réglage de la plate-forme pédagogique.

Lorsqu'un nouveau fichier est envoyé par l'action **Post user file**, le fichier le plus ancien de l'utilisateur est supprimé pour respecter le quota.

:::

## Get user file

Récupérer l'URL d'un fichier utilisateur à partir de son ID.

|Requête|Chemin|Headers|Valeur|
|-------|------|-------|------|
|GET|`/api/v1/users/secured_attachments/{ID}`|`Authorization`|`Bearer [REDACTED]`

:::note

Si l'ID ne correspond à aucun enregistrement ou si l'enregistrement n'est pas lié à l'utilisateur courant, la réponse serveur sera la suivante :

```js
{
  "status": {
    "code": 404,
    "message": "Couldn't find a record for the requested ID."
  }
}
```

:::
---
sidebar_position: 1
---

# Utilisateur

## Show

Récupérer les informations d'un utilisateur.

|Requête|Chemin|Headers|Valeur|
|-------|------|-------|------|
|POST|`/api/v1/users/oauth`|`Authorization`|`Bearer [REDACTED]`

```js title="Exemple de réponse"
{
  "user": {
    "id": 10,
    "firstname": "John",
    "lastname": "Doe",
    "email": "johndoe@localhost.com",
    "created_at": "2024-02-13T09:00:00.389Z"
  }
}
```

## User files

Récupérer la liste des fichiers d'un utilisateur.

|Requête|Chemin|Headers|Valeur|
|-------|------|-------|------|
|GET|`/api/v1/users/user_files`|`Authorization`|`Bearer [REDACTED]`

```js title="Exemple de réponse"
{
  "user_files": [
    {
      "id": 4,
      "attachment": "[REDACTED]/test_file.json",
      "file_type": "json",
      "created_at": "2024-06-06T14:00:00.751Z",
      "user": {
        "id": 10,
        "firstname": "John",
        "lastname": "Doe",
        "email": "johndoe@localhost.com",
        "created_at": "2024-06-06T14:00:00.544Z"
      }
    }
  ]
}
```

## Post user file

Envoyer un fichier utilisateur.

|Requête|Chemin|Headers|Valeur|
|-------|------|-------|------|
|POST|`/api/v1/users/user_files/upload`|`Authorization`|`Bearer [REDACTED]`

```js title="Exemple de réponse"
{
  "user_file": {
    "id": 4,
    "attachment": "[REDACTED]/test_file.json",
    "file_type": "json",
    "created_at": "2024-06-06T14:00:00.751Z",
    "user": {
      "id": 10,
      "firstname": "John",
      "lastname": "Doe",
      "email": "johndoe@localhost.com",
      "created_at": "2024-06-06T14:00:00.544Z"
    }
  }
}
```

:::note

Le nombre de fichiers qu'un utilisateur peut posséder dépend du réglage de la plate-forme pédagogique.

Lorsqu'un nouveau fichier est envoyé par l'action **Post user file**, le fichier le plus ancien de l'utilisateur est supprimé pour respecter le quota.

:::

## Show user file

Récupérer l'URL d'un fichier utilisateur à partir de son ID.

|Requête|Chemin|Headers|Valeur|
|-------|------|-------|------|
|POST|`/api/v1/users/secured_attachments/[ID]`|`Authorization`|`Bearer [REDACTED]`

```js title="Exemple de réponse"
{
  "attachment": "[REDACTED]/test_file.json"
}
```

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
---
sidebar_position: 2
---

# Spécifications

Spécifications pour l'émission de déclarations xAPI.

<sup>*</sup> *[REDACTED]* signifie que la donnée est privée (mot de passe, URL, ...).

## Authentification

Il est nécessaire d'identifier l'utilisateur concerné par la déclaration xAPI. Voir [Authentification OAuth2](../authentification/authentification-oauth2).

À partir des informations de l'utilisateur récupérées après un *Devise Authentication Flow* :

```js title="Infos utilisateur"
{
  "id": 1,
  "email": "john.doe@example.com",
  "firstname": "John",
  "lastname": "Doe",
  "created_at": "2023-11-06T15:49:07.837Z",
  "updated_at": "2023-12-07T09:13:02.592Z"
}
```

On peut collecter les valeurs `id` et `email` pour construire l'objet `Agent` à partir des infos d'authentification :

```js
{
    "objectType": "Agent",
    "mbox": "john.doe@example.com",
    "account": {
        "homePage": "http://[REDACTED]",
        "name": "1"
    }
}
```

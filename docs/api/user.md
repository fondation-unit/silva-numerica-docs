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
    "id": 1,
    "firstname": "User",
    "lastname": "Example",
    "email": "user.example@example.com",
    "created_at": "2024-02-13T09:04:08.389Z"
  }
}
```

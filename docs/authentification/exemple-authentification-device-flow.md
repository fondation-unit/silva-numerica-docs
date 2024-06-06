---
sidebar_position: 2
---

# Exemple d'authentification Device Flow

## 1. Requête d'autorisation de client

|Requête|URL|Paramètres|
|-------|---|----------|
|POST|`[API_URL]/oauth/authorize_device`|`client_id`|

#### Avec cURL :

```bash
curl -X POST https://[API_URL]/oauth/authorize_device \
  -H "Content-Type: application/json" \
  --data '{"client_id": "[REDACTED]"}'
```

## 2. Récupération des informations nécessaires

Récupérer à minima :

- `device_code` 
- `verification_uri_complete`

## 3. Lancement d'un polling sur l'URI de token

Lancer une requête répétée à l'intervale renvoyée par la réponse de l'étape 2 (toutes les 5 secondes par défaut).

<table>
  <thead>
    <tr>
      <th>Requête</th>
      <th>URL</th>
      <th>Paramètre</th>
      <th>Valeur</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="3">POST</td>
      <td rowspan="3">`[API_URL]/oauth/token`</td>
      <td>`grant_type`</td>
      <td>`urn:ietf:params:oauth:grant-type:device_code`</td>
    </tr>
    <tr>
      <td>`device_code`</td>
      <td>`[REDACTED]`</td>
    </tr>
    <tr>
      <td>`client_id`</td>
      <td>`[REDACTED]`</td>
    </tr>
  </tbody>
</table>

#### Avec cURL :

```bash
curl -X POST https://[API_URL]/oauth/token \
  -H "Content-Type: application/json" \
  --data '{"grant_type": "urn:ietf:params:oauth:grant-type:device_code", "device_code": "[REDACTED]", "client_id": "[REDACTED]"}'
```

#### Interprêter les résultats :

Un polling avec succès retournera les informations suivantes :

```js
{
  "access_token": "[REDACTED]",
  "token_type": "Bearer",
  "expires_in": 7200,
  "refresh_token": "[REDACTED]",
  "scope": "read",
  "created_at": 1707128830
}
```

Récupérer `access_token` pour authentifier l'utilisateur sur la plateforme pédagogique.

## 4. Affichage de l'interface de confirmation

Ouvrir un navigateur sur l'URL `verification_uri_complete` fournie en réponse à l'étape 2.

- L'utilisateur déjà authentifié devra valider le code pré-complété en cliquant sur le bouton.
- L'utilisateur non-authentifié devra se connecter à son compte puis valider la connexion en cliquant sur le bouton.

La validation avec succès par l'utilisateur déclenche la réception des informations attendues par le polling de l'étape 3.

## 5. Récupérer les informations de l'utilisateur sur la plate-forme pédagogique

:::warning
A ce stade, la requête est émise vers l'API de la plate-forme pédagogique et non le serveur d'authentification.
:::

Émettre une requête GET avec le Bearer token correspondant à la valeur `access_token` récupérée par le polling de l'étape 3.

|Requête|URL|Headers|Valeur|
|-------|---|-------|------|
|GET|`[API_URL]/api/v1/users/current_user`|`Authorization`|`Bearer [REDACTED]`|

#### Avec cURL :

```bash
curl https://[API_URL]/api/v1/users/current_user \
  -H "Authorization: Bearer [REDACTED]"
```

#### Exemple de réponse :

```js
{
  "id": 5,
  "email": "john.doe@example.com",
  "firstname": "John",
  "lastname": "Doe",
  "created_at": "2024-02-05T08:52:20.957Z",
  "created_date": "05/02/2024"
}
```

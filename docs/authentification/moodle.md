---
sidebar_position: 2
---

# Utilisation avec Moodle

Configuration de l'authentification OAuth2 dans Moodle.

<sup>*</sup> *[REDACTED]* signifie que la donnée est privée (mot de passe, URL, ...).

## Configuration

1. Activer le plugin d'authentification OAuth

2. Paramétrer les réglages suivants dans **Administration > Server > Services OAuth 2** :

|Keys|Values|
|----|------|
|Name|`[REDACTED]`|
|Client ID|`[REDACTED]`|
|Client Secret|`[REDACTED]`|
|Service base URL|`[REDACTED]`|
|This service will be used|`Login page and internal services`|
|Scopes included in a loginrequest|`read`|
|Scopes included in a login request for offline access|`read`|
|Require email verification|`true`|

3. Dans configurer les points de terminaison dans **Administration > Server > Services OAuth 2** :

|Keys|Values|
|----|------|
|discovery_endpoint|`https://[REDACTED]/oauth/applications`|
|authorization_endpoint|`https://[REDACTED]/oauth/authorize`|
|token_endpoint|`https://[REDACTED]/oauth/token`|
|revocation_endpoint|`https://[REDACTED]/oauth/revoke`|
|userinfo_endpoint|`https://[REDACTED]/api/v1/me.json`|

4. Configurer les correspondances de champs utilisateur dans **Administration > Server > Services OAuth 2** :

|Keys|Values|
|----|------|
|firstname|`firstname`|
|lastname|`firstname`|
|email|`email`|

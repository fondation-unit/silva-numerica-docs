---
sidebar_position: 2
---

# Scénarios et parcelles

## Cycle de création d'un scénario

**1. Créer un enregistrement de scénario vide pour récupérer son ID :**

|Requête|Chemin|Headers|Valeur|
|-------|------|-------|------|
|POST|`/api/v1/scenarii/create_id`|`Authorization`|`Bearer [REDACTED]`


**2. Mettre à jour l'enregistrement du scénario :**

|Requête|Chemin|Headers|Valeur|
|-------|------|-------|------|
|PATCH|`/api/v1/scenarii/{id}`|`Authorization`|`Bearer [REDACTED]`

Voir la liste des paramètres dans Swagger.

La mise à jour de l'enregistrement du scénario nécessite de fournir l'ID d'une parcelle existante.

Le paramètre concernant les *skills* (aptitudes) permet de spécifier les ID devant être associés au scénario. Récupérer les ID en interrogeant la route GET `/api/v1/skills`.

## Cycle de création d'une parcelle

Similaire à celui du scénario.

**1. Créer un enregistrement de parcelle vide pour récupérer son ID :**

|Requête|Chemin|Headers|Valeur|
|-------|------|-------|------|
|POST|`/api/v1/parcels/create_id`|`Authorization`|`Bearer [REDACTED]`


**2. Mettre à jour l'enregistrement de la parcelle :**

|Requête|Chemin|Headers|Valeur|
|-------|------|-------|------|
|PATCH|`/api/v1/parcels/{id}`|`Authorization`|`Bearer [REDACTED]`

Voir la liste des paramètres dans Swagger.

Les paramètres concernant les *zones* et les *espèces* (species) nécessitent uniquement de renseigner leur nom. Si le nom correspondant à une zone ou une espèce est déjà existant, la clé étrangère sera automatiquement employée. Sinon, un nouvel enregistrement sera créé pour stocker la ou les nouvelles zones ou espèces.

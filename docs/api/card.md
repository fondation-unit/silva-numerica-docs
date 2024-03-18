---
sidebar_position: 2
---

# Cartes

## Index

Récupérer la liste des cartes.

|Requête|Chemin|Headers|Valeur|
|-------|------|-------|------|
|GET|`/api/v1/cards`|`Authorization`|`Bearer [REDACTED]`

```js title="Exemple de réponse"
{
  "cards": [
    {
      "id": 1,
      "name": "Chêne sessile",
      "type": "flore",
      "created_at": "2024-03-15T14:40:38.446Z",
      "updated_at": "2024-03-15T14:46:27.694Z"
    },
    {
      "id": 2,
      "name": "Chêne rouge d'Amérique",
      "type": "flore",
      "created_at": "2024-03-15T14:40:39.446Z",
      "updated_at": "2024-03-15T14:40:39.446Z"
    }
  ]
}
```

## Show

Récupérer les informations d'une carte à partir de son ID.

|Requête|Chemin|Headers|Valeur|
|-------|------|-------|------|
|GET|`/api/v1/cards/[ID]`|`Authorization`|`Bearer [REDACTED]`

```js title="Exemple de réponse"
{
  "card": {
    "id": 1,
    "name": "Chêne sessile",
    "type": "flore",
    "latin_name": "Quercus petraea",
    "latin_name_author": "(Mattuschka) Liebl",
    "other_common_names": "Chêne lombard, chêne cerris, chêne de bourgogne, chêne de turquie, doucier",
    "bibliographical_sources": "Eos hic est. In *incidunt* est. Velit aut consequatur.",
    "family": "adoxacées",
    "type_attributes": {
      "id": 1,
      "age_min": 500,
      "age_max": 1000,
      "age_range": "between",
      "height_min": 25,
      "height_max": 40,
      "height_range": "between",
      "height_unit": "m",
      "features": [
        {
          "lifespan": {
            "id": 227,
            "name": "lifespan",
            "name_fr": "durée de vie",
            "value": "plante bisannuelle"
          }
        },
        {
          "vegetative_rest_state": {
            "id": 230,
            "name": "vegetative_rest_state",
            "name_fr": "état durant le repos végétatif",
            "value": "espèce sempervirente"
          }
        },
        {
          "flowering_sporulation": {
            "entries": [
              "mars",
              "mai",
              "juin"
            ],
            "name": "floraison / sporulation"
          }
        },
        {
          "stump_image": {
            "image": "[REDACTED]/quercus_cerris-stump.jpg",
            "name": "souche",
            "description": null
          }
        },
        {
          "bark_image": {
            "image": "[REDACTED]/quercus_cerris-bark.jpg",
            "name": "écorce",
            "description": [
              "sombre",
              "brun grisâtre",
              "profondément rainurée"
            ]
          }
        },
        {
          "twig_image": null
        },
        {
          "stem_image": null
        },
        {
          "stalk_image": null
        },
        {
          "bud_image": null
        },
        {
          "leaf_image": {
            "image": "[REDACTED]/quercus_cerris-leaf.jpg",
            "name": "feuille",
            "description": [
              "lisse",
              "verdâtre"
            ]
          }
        },
        {
          "flower_image": null
        },
        {
          "inflorescence_image": null
        },
        {
          "fruit_image": null
        },
        {
          "seed_image": null
        },
        {
          "feature_type": {
            "name": "biological_type",
            "name_fr": "type biologique",
            "entries": [
              {
                "id": 14,
                "value": "hémicryptophyte"
              }
            ]
          }
        },
        {
          "feature_type": {
            "name": "pollination_method",
            "name_fr": "mode de pollinisation",
            "entries": [
              {
                "id": 17,
                "value": "autogamie"
              },
              {
                "id": 18,
                "value": "allogamie"
              }
            ]
          }
        },
        {
          "feature_type": {
            "name": "diaspores_dispersal_mode",
            "name_fr": "mode de dispersion des diaspores",
            "entries": [
              {
                "id": 21,
                "value": "géochorie"
              }
            ]
          }
        },
        {
          "feature_type": {
            "name": "light",
            "name_fr": "lumière",
            "entries": [
              {
                "id": 37,
                "value": "photophile"
              }
            ]
          }
        },
        {
          "feature_type": {
            "name": "humus_form",
            "name_fr": "forme d'humus",
            "entries": [
              {
                "id": 43,
                "value": "dysmull"
              }
            ]
          }
        },
        {
          "feature_type": {
            "name": "trophic_level",
            "name_fr": "niveau trophique",
            "entries": [
              {
                "id": 80,
                "value": "riche en azote"
              }
            ]
          }
        },
        {
          "feature_type": {
            "name": "water_level",
            "name_fr": "niveau d'hydrique",
            "entries": [
              {
                "id": 87,
                "value": "frais"
              }
            ]
          }
        },
        {
          "feature_type": {
            "name": "materials",
            "name_fr": "matériaux",
            "entries": [
              {
                "id": 104,
                "value": "limons (purs, sableux ou caillouteux)"
              }
            ]
          }
        },
        {
          "feature_type": {
            "name": "indicative_characteristic",
            "name_fr": "caractère indicateur",
            "entries": [
              {
                "id": 132,
                "value": "espèce mésophile"
              }
            ]
          }
        },
        {
          "feature_type": {
            "name": "ecological_succession_stage",
            "name_fr": "stade de succession écologique",
            "entries": [
              {
                "id": 144,
                "value": "espèce dryade"
              }
            ]
          }
        },
        {
          "feature_type": {
            "name": "biotope",
            "name_fr": "biotope",
            "entries": [
              {
                "id": 149,
                "value": "bois frais"
              }
            ]
          }
        },
        {
          "feature_type": {
            "name": "station",
            "name_fr": "station",
            "entries": [
              {
                "id": 223,
                "value": "plaine"
              }
            ]
          }
        },
        {
          "feature_type": {
            "name": "pollen_grain_transport",
            "name_fr": "mode de transport des grains de pollen",
            "entries": [
              {
                "id": 31,
                "value": "hydrogamie"
              },
              {
                "id": 32,
                "value": "zoogamie"
              }
            ]
          }
        },
        {
          "feature_type": {
            "name": "growth_form",
            "name_fr": "forme de croissance",
            "entries": [
              {
                "id": 9,
                "value": "arbuste"
              }
            ]
          }
        },
        {
          "feature_type": {
            "name": "floral_group",
            "name_fr": "groupe",
            "entries": [
              {
                "id": 3,
                "value": "angiospermes"
              }
            ]
          }
        },
        {
          "feature_type": {
            "name": "reproduction",
            "name_fr": "reproduction",
            "entries": [
              {
                "id": 232,
                "value": "reproduction sexuée"
              },
              {
                "id": 235,
                "value": "monoïque"
              }
            ]
          }
        }
      ]
    },
    "created_at": "2024-03-15T14:40:38.446Z",
    "updated_at": "2024-03-15T14:46:27.694Z"
  }
}
```

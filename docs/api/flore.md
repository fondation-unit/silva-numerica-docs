---
sidebar_position: 2
---

# Cartes flore

## Index

Récupérer la liste des cartes de type flore.

|Requête|Chemin|Headers|Valeur|
|-------|------|-------|------|
|GET|`/api/v1/floras`|`Authorization`|`Bearer [REDACTED]`

```js title="Exemple de réponse"
{
  "floras": [
    {
      "created_at": "08/02/2024 - 12:01",
      "updated_at": "13/02/2024 - 14:01",
      "id": 1,
      "name": "Chêne chevelu"
    },
    {
      "created_at": "09/02/2024 - 12:00",
      "updated_at": "14/02/2024 - 14:00",
      "id": 2,
      "name": "Chêne rouge d'Amérique"
    }
  ]
}
```

## Show

Récupérer les informations d'une carte de type flore à partir de son ID.

|Requête|Chemin|Headers|Valeur|
|-------|------|-------|------|
|GET|`/api/v1/flora/[ID]`|`Authorization`|`Bearer [REDACTED]`

```js title="Exemple de réponse"
{
  "flora": {
    "created_at": "08/02/2024 - 12:02",
    "updated_at": "13/02/2024 - 14:02",
    "id": 1,
    "age_min": 150,
    "age_max": 200,
    "age_range": "between",
    "height_min": 25,
    "height_max": 40,
    "height_range": "between",
    "height_unit": "m",
    "single_features": [
      {
        "lifespan": {
          "id": 189,
          "name": "lifespan",
          "name_fr": "durée de vie",
          "value": "plante vivace"
        }
      },
      {
        "subsistance": {
          "id": 192,
          "name": "subsistance",
          "name_fr": "subsistance",
          "value": "espèce caducifoliée"
        }
      },
      {
        "sexual_reproduction": {
          "id": 196,
          "name": "sexual_reproduction",
          "name_fr": "reproduction sexuée",
          "value": "monoïque"
        }
      },
      {
        "vegetative_reproduction": {
          "id": 199,
          "name": "vegetative_reproduction",
          "name_fr": "reproduction végétative",
          "value": "drageonnant"
        }
      },
      {
        "flowering_sporulation": {
          "entries": [
            "mai",
            "juin"
          ],
          "name": "floraison / sporulation"
        }
      },
      {
        "stump_image": {
          "image": null,
          "name": "image souche",
          "description": "lisse et verdâtre\r\nmince"
        }
      },
      {
        "bark_image": {
          "image": null,
          "name": "image écorce",
          "description": null
        }
      },
      {
        "twig_image": {
          "image": "[REDACTED]/image.jpg",
          "name": "image rameau",
          "description": null
        }
      },
      {
        "stalk_image": {
          "image": null,
          "name": "image pétiole",
          "description": null
        }
      },
      {
        "bud_image": {
          "image": "[REDACTED]/image.jpg",
          "name": "image bourgeon",
          "description": null
        }
      },
      {
        "leaf_image": {
          "image": "[REDACTED]/image.jpg",
          "name": "image feuille",
          "description": null
        }
      },
      {
        "flower_image": {
          "image": null,
          "name": "image fleur / sore",
          "description": null
        }
      },
      {
        "inflorescence_image": {
          "image": null,
          "name": "image inflorescence",
          "description": null
        }
      },
      {
        "fruit_image": {
          "image": null,
          "name": "image fruit",
          "description": null
        }
      },
      {
        "seed_image": {
          "image": null,
          "name": "image graine",
          "description": null
        }
      }
    ],
    "twig_illustration": {
      "image": "[REDACTED]/image.jpg",
      "name": "illustration rameau"
    },
    "structure_illustration": {
      "image": "[REDACTED]/image.jpg",
      "name": "illustration structure générale"
    },
    "leaf_illustration": {
      "image": "[REDACTED]/image.jpg",
      "name": "illustration feuille"
    },
    "seed_illustration": {
      "image": null,
      "name": "illustration graine"
    },
    "card": {
      "id": 1,
      "name": "Chêne chevelu",
      "latin_name": "Quercus cerris",
      "other_common_names": "Chêne lombard, Chêne cerris, Chêne de Bourgogne, Chêne de Turquie, Doucier",
      "bibliographical_sources": "Facere voluptatem et. Et ~eveniet~ maxime. Aspernatur nihil sed.",
      "family": {
        "name": "fagacées"
      }
    },
    "multiple_features": [
      {
        "feature_type": {
          "name": "biological_type",
          "name_fr": "type biologique",
          "entries": [
            {
              "id": 9,
              "value": "phanérophyte"
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
              "id": 12,
              "value": "anémogame"
            }
          ]
        }
      },
      {
        "feature_type": {
          "name": "dissemination_mode",
          "name_fr": "mode de dispersion / dissémination",
          "entries": [
            {
              "id": 21,
              "value": "zoochore"
            },
            {
              "id": 23,
              "value": "gravité"
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
              "id": 24,
              "value": "demi-ombre"
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
              "id": 3,
              "value": "petit arbre"
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
              "id": 110,
              "value": "bois"
            },
            {
              "id": 112,
              "value": "bois frais"
            },
            {
              "id": 113,
              "value": "bois humides"
            },
            {
              "id": 116,
              "value": "bords des eaux"
            },
            {
              "id": 117,
              "value": "bords des étangs"
            },
            {
              "id": 119,
              "value": "bords des rivières"
            },
            {
              "id": 121,
              "value": "bords des tourbières"
            },
            {
              "id": 128,
              "value": "coupes forestières"
            },
            {
              "id": 129,
              "value": "coupes forestières plus ou moins humides"
            },
            {
              "id": 140,
              "value": "forêts feuillues"
            },
            {
              "id": 141,
              "value": "forêts feuillues mélangées"
            },
            {
              "id": 142,
              "value": "forêts mélangées"
            },
            {
              "id": 144,
              "value": "forêts résineuses"
            },
            {
              "id": 145,
              "value": "forêts ripicoles"
            },
            {
              "id": 150,
              "value": "friches"
            },
            {
              "id": 153,
              "value": "groupements de rochers ombragés"
            },
            {
              "id": 162,
              "value": "lisières forestières"
            },
            {
              "id": 165,
              "value": "marais"
            },
            {
              "id": 168,
              "value": "ourlets"
            },
            {
              "id": 184,
              "value": "taillis secs"
            }
          ]
        }
      },
      {
        "feature_type": {
          "name": "acidity_level",
          "name_fr": "niveau d'acivité (pH)",
          "entries": [
            {
              "id": 202,
              "value": "légèrement acide"
            },
            {
              "id": 203,
              "value": "assez riche en bases"
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
              "id": 204,
              "value": "riche en éléments nutritifs"
            },
            {
              "id": 205,
              "value": "plus ou moins riche en éléments nutritifs"
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
              "id": 206,
              "value": "drainé"
            },
            {
              "id": 207,
              "value": "frais"
            },
            {
              "id": 208,
              "value": "assez frais"
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
              "id": 209,
              "value": "argiles"
            },
            {
              "id": 210,
              "value": "limons"
            },
            {
              "id": 211,
              "value": "limons sableux"
            },
            {
              "id": 212,
              "value": "sables"
            },
            {
              "id": 213,
              "value": "silices (pures ou pierreuses)"
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
              "id": 93,
              "value": "espèce à large amplitude"
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
              "id": 105,
              "value": "espèce pionnière"
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
              "id": 186,
              "value": "plaine"
            }
          ]
        }
      }
    ]
  }
}
```

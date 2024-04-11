---
sidebar_position: 2
---

# Cartes

## Index

Récupérer la liste des cartes.

|Requête|Chemin|Headers|Valeur|
|-------|------|-------|------|
|GET|`/api/v1/cards`|`Authorization`|`Bearer [REDACTED]`

```js title="Exemple de réponse d'une carte de type Flore"
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
  "flora": {
    "id": 1,
    "type": "flore",
    "created_at": "2024-04-08T09:51:15.161Z",
    "updated_at": "2024-04-08T10:01:07.230Z",
    "illustrations": [
      {
        "url": "[REDACTED]/structure.jpg",
        "name": "Structure générale"
      },
      {
        "url": "[REDACTED]/twig.jpg",
        "name": "Tige / rameau"
      },
      {
        "url": "[REDACTED]/leaf.jpg",
        "name": "Feuille / fronde / aiguille"
      },
      {
        "url": "[REDACTED]/flower.jpg",
        "name": "Fleur / sore"
      },
      {
        "url": "[REDACTED]/fruit.jpg",
        "name": "Fruit"
      }
    ],
    "general_informations": {
      "title": "Informations générales",
      "entries": {
        "name": "Chêne sessile",
        "latin_name": "Quercus petraea",
        "latin_name_author": "(Mattuschka) Liebl",
        "scientific_name": "Quercus petraea (Mattuschka) Liebl",
        "other_common_names": "Chêne lombard, chêne cerris, chêne de bourgogne, chêne de turquie, doucier",
        "group": {
          "name_fr": "Groupe",
          "values": [
            "Gymnospermes"
          ]
        },
        "family": "Fagacées"
      }
    },
    "biological_characteristics": {
      "title": "Caractères biologiques",
      "entries": {
        "growth_form": {
          "name_fr": "Forme de croissance",
          "values": [
            "Arbrisseau"
          ]
        },
        "vegetative_rest_state": {
          "name_fr": "État durant le repos végétatif",
          "value": "Espèce caducifoliée"
        },
        "lifespan": {
          "name_fr": "Durée de vie",
          "value": "Plante vivace"
        },
        "biological_type": {
          "name_fr": "Type biologique",
          "values": [
            "Phanérophyte"
          ]
        },
        "longevity": {
          "name_fr": "Longévité biologique",
          "value": "Entre 500 et 1000 ans"
        }
      }
    },
    "reproductive_functions": {
      "title": "Fonctions reproductives",
      "entries": {
        "reproduction": {
          "name_fr": "Reproduction",
          "values": [
            "Reproduction sexuée",
            "Monoïque"
          ]
        },
        "pollination_method": {
          "name_fr": "Mode de pollinisation",
          "values": [
            "Autogamie",
            "Allogamie"
          ]
        },
        "pollen_grain_transport": {
          "name_fr": "Mode de transport des grains de pollen",
          "values": [
            "Hydrogamie",
            "Zoogamie",
            "Ornithogamie"
          ]
        },
        "diaspores_dispersal_mode": {
          "name_fr": "Mode de dispersion des diaspores",
          "values": [
            "Barochorie",
            "Hydrochorie"
          ]
        }
      }
    },
    "flowering_sporulation": {
      "name_fr": "Floraison / Sporulation",
      "values": [
        "Mars",
        "Mai",
        "Juin"
      ]
    },
    "diagnostic_features": {
      "title": "Caractères diagnostiques",
      "entries": {
        "height": {
          "name_fr": "Taille",
          "value": "Entre 25 m et 40 m"
        },
        "bark_image": null,
        "twig_image": null,
        "bud_image": null,
        "leaf_image": {
          "url": "[REDACTED]/leaf-2.jpg",
          "name_fr": "feuille / fronde / aiguille",
          "description": null
        },
        "stalk_image": null,
        "flower_image": null,
        "fruit_image": {
          "url": "[REDACTED]/fruit.png",
          "name_fr": "fruit",
          "description": null
        },
        "seed_image": null
      }
    },
    "autoecology": {
      "name_fr": "Autécologie",
      "entries": {
        "light": {
          "name_fr": "Lumière",
          "values": [
            "Photophile"
          ]
        },
        "humus_form": {
          "name_fr": "Forme d'humus",
          "values": [
            "Hydromor"
          ]
        },
        "soil_texture": {
          "name_fr": "Texture du sol",
          "values": [
            "Équilibrée"
          ]
        },
        "trophic_gradient": {
          "name_fr": "Gradient trophique",
          "values": "Acide à très acide"
        },
        "hydric_gradient": {
          "name_fr": "Gradient hydrique",
          "values": "Humide à assez humide"
        },
        "trophic_indicator_characteristic": {
          "name_fr": "Caractère indicateur trophique",
          "values": "Neutronitrophile à mésoacidiphile"
        },
        "hydric_indicator_characteristic": {
          "name_fr": "Caractère indicateur hydrique",
          "values": "Mésoxérophile à mésohygrocline"
        }
      }
    },
    "biotopes": {
      "name_fr": "Biotopes",
      "values": []
    },
    "stations": {
      "name_fr": "Stations",
      "values": [
        "Forêt humide"
      ]
    },
    "usages_properties": {
      "name_fr": "Usages / propriétés",
      "values": []
    },
    "protection": {
      "name_fr": "Protection",
      "values": [
        "Protection régionale"
      ]
    },
    "red_list": {
      "name_fr": "Liste rouge des espèces menacées (france métropolitaine)",
      "value": "VU : vulnérable",
      "background_color": "#f7c729",
      "border_color": "#f7c729"
    },
    "bibliographical_sources": "Ratione consequatur pariatur. Quos temporibus aut. Dicta voluptas ~voluptas.~"
  }
}
```

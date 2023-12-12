---
sidebar_position: 1
---

# Intro

La norme xAPI (Experience API) emploie le format de données JSON (JavaScript Object Notation), pour faciliter l'interopérabilité entre systèmes.

xAPI permet de suivre des activités d'apprentissage en ligne classiques (au même titre que SCORM) mais également des activités en provenance d'autres systèmes ou hors ligne.

La structure des déclarations xAPI (*statements*) est construite autour du couple **acteur-verbe-objet**, où l'acteur décrit la personne à l'origine d'une action, le verbe décrit l'action effectuée (par exemple, *"lu"* ou *"répondu"*) et l'objet décrit l'entité sur laquelle à eu lieu l'action décrite par le verbe.

À cela se greffent des données suplémentaires comme l'*agent* (acteur de l'action), le résultat, le score, etc.

## Verbe

### Présentation

Un système (par exemple un LRS) lisant une déclaration (*statement*) xAPI doit utiliser l'IRI (*Identifiants de Ressources Internationalisés*) du verbe la composant pour en déduire la signification.

<table>
  <tr>
      <td>Exemple d’IRI</td>
      <td>http://adlnet.gov/expapi/verbs/answered</td>
  </tr>
  <tr>
      <td>Représentation lisible</td>
      <td>answered</td>
  </tr>
</table>

On observe au passage que, comme stipulé dans la norme, une IRI doit contenir une portion humainement interprétable pour lever toute ambiguïté (dans notre exemple, la terminaison `answered` de l’IRI après le dernier `/`).

Un IRI ne doit servir à décrire qu’une seule signification.

Exemple d’expression JSON décrivant l’utilisation d’un verbe :

```js
{
    "id": "http://activitystrea.ms/schema/1.0/read", 
    "display": {
        "en-US": "read",
        "fr": "lu" 
    } 
}
```

### Liste des verbes

La liste des verbes proposés dans le registre officiel est limitée à ceux employés par [ADL](https://www.adlnet.gov/about/) :
https://registry.tincanapi.com/#home/verbs

Néanmoins, xAPI permet de la compléter et d'employer d'autres verbes en interne pour décrire les actions non répertoriées.

## Objet

L’objet définit l’élément sur lequel une interaction a été produite. Il répond à l’un des types suivants (`objectType`) :
- activité (*Activity*)
- agent ou groupe (*Agent*, *Group*)
- sous-déclaration (*SubStatement*)
- référence à une autre déclaration (*StatementRef*)

Une activité doit être **identifiée par une URI unique** (attribut `id`) et peut être accompagnée d'informations descriptives.

```js
{
    "objectType": "Activity",
    "id": "http://example.com/audios/text-comprehension.mp3", 
    "definition": {
        "name": {
            "en-US": "A listening comprehension audio file"
        }
    }
}
```

L'ID unique d'une activité doit permettre d'interroger les données et d'éviter des pertes statistique ou des compromissions de données.

La définition d'une activité peut être agrémentée de 
- `name` : objet `langue: description`
- `type` : URI identifiant un type prédéfini https://registry.tincanapi.com/#home/activityTypes
- `description` : objet `langue: description` proposant une description plus complète que l'attribut `name`
- `extensions` : champ permettant d'ajouter du contexte à une activité (par exemple, le cours dans lequel elle s'insère), sours la forme `URI: id|objet`

Exemple :

```js
{
    "objectType": "Activity",
    "id": "http://example.com/audios/text-comprehension.mp3", 
    "definition": {
        "name": {
            "en-US": "A listening comprehension audio file",
            "fr": "Fichier audio de compréhension orale"
        }
        "type": "http://activitystrea.ms/schema/1.0/audio",
        "description": {
            "en-US": "Listening comprehension of a text by a famous author",
            "fr": "Compréhension orale d'un texte d'un auteur célèbre"
        },
        "extensions": {
            "http://example.com/courses/text-comprehension": "id-10"
        }
    }
}
```

Exemple d'extension plus complèxe :

```js
{
    ...
    "definition": {
        ...
        "extensions": {
            "http://id.tincanapi.com/extension/powered-by": {
                "name": "xAPI Engine",
                "homePage": "../lrs-lms/lrs-for-lmss-home/",
                "version": "2012.1.0.5039b"
            }
        },
        "version" : [ "1.0.0" ]
    }
}
```

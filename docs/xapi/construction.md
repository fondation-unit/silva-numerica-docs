---
sidebar_position: 3
---

# Construction

Spécifications pour la construction de déclarations xAPI.

Outil générateur de statements : https://adlnet.github.io/xapi-lab/

## Acteur

> Spécifications : https://github.com/adlnet/xAPI-Spec/blob/master/xAPI-Data.md#242-actor
---
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

On peut collecter les valeurs `id` et `email` pour construire l'objet `actor` à partir des infos d'authentification :

```js
"actor": {
    "objectType": "Agent",
    "mbox": "john.doe@example.com",
    "account": {
        "homePage": "http://example.com/users/1",
        "name": "1"
    }
}
```

## Verbe

> Spécifications https://github.com/adlnet/xAPI-Spec/blob/master/xAPI-Data.md#243-verb
---
À partir de la [liste des verbes](../xapi/liste-des-verbes), identifier celui correspondant à l'action à décrire.

Construire l'objet `verb` et spécifier la traduction française. Exemple :

```js
"verb": {
    "id": "ttp://adlnet.gov/expapi/verbs/answered",
    "display": {
        "en-US": "answered",
        "fr": "répondu",
    }
}
```

## Objet

> Spécifications : https://github.com/adlnet/xAPI-Spec/blob/master/xAPI-Data.md#244-object
---
Un objet peut être de 4 types (voir [Introduction](../xapi/intro)).

### Activity

Permet de représenter une activité comme objet de la déclaration.

|Propriété|Type|Description|Requis|
|---------|----|-----------|-------|
|objectType|String|MUST be Activity when present|non|
|id|IRI|Identifiant unique pour une activité|oui|
|definition|Object|Métadonnées, voir exemple ci-dessous|non|

```js title="Exemple d'objet de type Activity"
"object": {
    // highlight-start
    "objectType": "Activity",
    // highlight-end
    "id": "http://example.com/objects/custom_resource",
    "definition": {
        "name": {
            "en-US": "Definition name",
            "fr": "Nom de la définition"
        },
        "type": "http://id.tincanapi.com/activitytype/book",
        "description": {
            "en-US": "Object description",
            "fr": "Description de l'objet"
        },
        "extensions": {
            "http://example.com/courseId": "10",
            "http://example.com/contextId": "75"
        }
    }
}
```

### Agent / Group

Le contenu d'un objet de type `Agent` est équivalent à l'objet Agent de la déclaration, auquel il faut obligatoirement ajouter la propriété `"objectType": "Agent"`.

```js title="Exemple d'objet de type Agent"
"object": {
    // highlight-start
    "objectType": "Agent",
    // highlight-end
    "mbox": "mailto:tyler.mulligan.ctr@adlnet.gov",
    "account": {
        "name": "xapiguy",
        "homePage": "http://example.com"
    },
    "name": "Tyler"
}
```

Le contenu d'un objet de type `Group` est équivalent et permet de spécifier un tableau des agents membres (`member`) :

```js title="Exemple d'objet de type Group"
"object": {
    // highlight-start
    "objectType": "Group",
    // highlight-end
    "mbox": "mailto:teamxapi@example.com",
    "name": "The group name",
    "member": [
        {
            "name": "Bob",
            "account": {
                "homePage": "http://www.example.com",
                "name": "13936749"
            },
            "objectType": "Agent"
        },
        {
            "name": "Carol",
            "openid": "http://carol.openid.example.org/",
            "objectType": "Agent"
        },
        {
            "name": "Tom",
            "mbox": "mailto:tom@example.com",
            "objectType": "Agent"
        },
        {
            "name": "Alice",
            "mbox_sha1sum": "ebd31e95054c018b10727de4db3ef2ec3a016ee9",
            "objectType": "Agent"
        }
    ]
}
```

### StatementRef

> Spécifications : https://github.com/adlnet/xAPI-Spec/blob/master/xAPI-Data.md#statement-references
---
Permet de définir une nouvelle déclaration en référence à une déclaration existante.

```js title="Exemple d'objet de type StatementRef"
"object": {
    "actor": { 
        "objectType": "Agent", 
        "mbox": "mailto:test@example.com" 
    },
    "verb": { 
        "id":"http://example.com/commented", 
        "display": {
            "en-US": "commented"
        } 
    },
    "object": {
        // highlight-start
        "objectType": "StatementRef",
        "id": "8f87ccde-bb56-4c2e-ab83-44982ef22df0"
        // highlight-end
    },
    "result": { 
        "response": "Wow, nice work!" 
    }
}
```

### SubStatement

> Spécifications : https://github.com/adlnet/xAPI-Spec/blob/master/xAPI-Data.md#substatements
---
Le type `SubStatement` permet de faire une référence à une déclaration déjà existante.
Cela permet de décrire, par exemple : 

> *John à commenté l'action* "*Bob à lu un livre*"

```js title="Exemple d'objet de type SubStatement"
"object": {
    // highlight-start
    "object_type": "SubStatement",
    // highlight-end
    "actor": {
        "object_type": "Agent",
        "name": "John Doe",
        "mbox": "mailto:john.doe@example.com"
    },
    "verb": {
        "id": "http://adlnet.gov/expapi/verbs/commented",
        "display": {
            "en-US": "commented"
        }
    },
    "object": {
        // highlight-start
        "object_type": "StatementRef",
        "id": "e05aa883-acaf-40ad-bf54-02c8ce485fb0"
        // highlight-end
    }
}
```

Dans le cas d'un type `SubStatement`, l'objet `object` doit être de type `StatementRef` et définir l'`id` correspondant à la déclaration de référence (*UUID du statement*).

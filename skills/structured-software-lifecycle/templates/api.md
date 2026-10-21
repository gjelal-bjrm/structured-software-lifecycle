# [Nom du projet] — Définition des API

Adresse de base : `[https://…/api]`
Authentification : [comment l'utilisateur est identifié]

## GET : lire

### [Titre : ce que fait l'API]

- **Quand** : [écran / action]
- **Adresse** : `GET /ressources?page=0&size=20`
- **Droits** : [qui peut l'appeler]
- **Paramètres** : [liste]
- **Réponse** :

```json
{
  "items": [],
  "page": 0,
  "size": 20,
  "total": 0
}
```

- **Erreurs** : 401 non connecté, 403 pas les droits, 404 introuvable

## POST : créer

### [Titre]

- **Quand** :
- **Adresse** : `POST /ressources`
- **Droits** :
- **Données envoyées** :

```json
{}
```

- **Réponse** :
- **Erreurs** :

## PUT / PATCH : modifier

## DELETE : supprimer

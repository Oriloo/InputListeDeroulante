# InputListeDeroulante-1.0

La bibliothèque `InputListeDeroulante-1.0` permet de créer un champ de saisie avec une liste déroulante personnalisée. Elle offre des options de sélection multiple, de recherche, et diverses personnalisations pour rendre vos formulaires plus interactifs.

[Voir la démo](https://oriloo.github.io/InputListeDeroulante-1.0/)

## Installation

Pour utiliser la bibliothèque, il suffit d'inclure les fichiers CSS et JavaScript dans votre projet.

```html
<link rel="stylesheet" href="path/to/InputListeDeroulante.css">
<script src="path/to/InputListeDeroulante.js"></script>
```

## Utilisation

### Exemple de base

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sélectionner des Éléments</title>
    <link rel="stylesheet" href="path/to/InputListeDeroulante.css">
</head>
<body>
    <form action="" method="post">
        <div id="container1"></div>
        <button type="submit">Submit</button>
    </form>

    <script src="path/to/InputListeDeroulante.js"></script>
    <script>
        InputListeDeroulante(document.querySelector('#container1'), {
            liste: ['Action', 'Comédie', 'Drame', 'Fantastique', 'Horreur', 'Romance', 'Science-fiction'],
            id: 'input1',
            name: 'elements1',
            placeholder: 'Sélectionnez des éléments',
            customClass: 'my-custom-class',
            required: true,
            requiredMax: 5,
            requiredMin: 1,
            searchable: true,
            noResultsText: 'Aucun résultat trouvé',
            customButtonLabel: 'Choisir',
            preselect: ['Action', 'Drame', 'Fantastique']
        });
    </script>
</body>
</html>
```

## Options

### `liste`
- **Type**: `Array<String>`
- **Description**: La liste des éléments à afficher dans la liste déroulante.
- **Exemple**: `['Action', 'Comédie', 'Drame', 'Fantastique', 'Horreur', 'Romance', 'Science-fiction']`

### `id`
- **Type**: `String`
- **Description**: L'identifiant unique de l'input text.
- **Exemple**: `'input1'`

### `name`
- **Type**: `String`
- **Description**: Le nom de l'input text pour la soumission du formulaire.
- **Exemple**: `'elements1'`

### `placeholder`
- **Type**: `String`
- **Description**: Le texte affiché lorsque le champ est vide.
- **Exemple**: `'Sélectionnez des éléments'`

### `customClass`
- **Type**: `String`
- **Description**: Une classe CSS personnalisée à ajouter au conteneur.
- **Exemple**: `'my-custom-class'`

### `required`
- **Type**: `Boolean`
- **Description**: Indique si le champ est requis.
- **Exemple**: `true`

### `requiredMax`
- **Type**: `Number`
- **Description**: Le nombre maximum de sélections autorisées.
- **Exemple**: `5`

### `requiredMin`
- **Type**: `Number`
- **Description**: Le nombre minimum de sélections requises.
- **Exemple**: `1`

### `searchable`
- **Type**: `Boolean`
- **Description**: Ajoute une barre de recherche pour filtrer les options.
- **Exemple**: `true`

### `noResultsText`
- **Type**: `String`
- **Description**: Texte affiché lorsqu'aucun résultat n'est trouvé dans la recherche.
- **Exemple**: `'Aucun résultat trouvé'`

### `customButtonLabel`
- **Type**: `String`
- **Description**: Personnalise le texte du bouton pour ouvrir la liste déroulante.
- **Exemple**: `'Choisir'`

### `preselect`
- **Type**: `Array<String>`
- **Description**: Éléments présélectionnés dans la liste déroulante.
- **Exemple**: `['Action', 'Drame', 'Fantastique']`

## Fonctionnement

1. **Création du conteneur** : La bibliothèque crée une structure pour l'input et la liste déroulante.
2. **Initialisation des éléments** : Le champ input et la liste déroulante sont construits selon les options passées.
3. **Gestion des événements** :
    - **Clic sur le bouton** : Ouvre/ferme la liste déroulante.
    - **Recherche** : Permet de filtrer les éléments via une barre de recherche.
    - **Sélection** : Les utilisateurs peuvent sélectionner ou désélectionner des éléments.
    - **Clic extérieur** : Ferme la liste déroulante en cas de clic en dehors de celle-ci.
4. **Mise à jour des sélections** : Met à jour les éléments sélectionnés dans le formulaire.
5. **Validation** : Vérifie les contraintes (`required`, `requiredMax`, `requiredMin`) à la soumission.

## Méthode d'utilisation

Appelez simplement la fonction `InputListeDeroulante` en lui passant le conteneur cible et un objet de configuration. Cette bibliothèque vous permet de créer des sélecteurs dynamiques avec des fonctionnalités avancées comme la recherche et la gestion des contraintes de sélection.

```javascript
InputListeDeroulante(document.querySelector('#container'), {
    liste: ['Option1', 'Option2'],
    id: 'input1',
    name: 'selectName',
    required: true,
    requiredMax: 3,
    searchable: true
});
```
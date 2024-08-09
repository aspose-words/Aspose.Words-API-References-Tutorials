---
title: Ajouter une forme de groupe
linktitle: Ajouter une forme de groupe
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment ajouter des formes de groupe aux documents Word à l'aide d'Aspose.Words for .NET avec ce didacticiel complet étape par étape.
type: docs
weight: 10
url: /fr/net/programming-with-shapes/add-group-shape/
---
## Introduction

Créer des documents complexes avec des éléments visuels riches peut parfois s'avérer une tâche ardue, en particulier lorsqu'il s'agit de formes de groupe. Mais n’ayez crainte ! Aspose.Words for .NET simplifie ce processus, le rendant aussi simple que bonjour. Dans ce didacticiel, nous vous guiderons à travers les étapes pour ajouter des formes de groupe à vos documents Word. Prêt à plonger ? Commençons !

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1.  Aspose.Words pour .NET : vous pouvez le télécharger à partir du[Page des versions d'Aspose](https://releases.aspose.com/words/net/).
2. Environnement de développement : Visual Studio ou tout autre IDE compatible avec .NET.
3. Compréhension de base de C# : Une connaissance de la programmation C# est un plus.

## Importer des espaces de noms

Pour commencer, nous devons importer les espaces de noms nécessaires dans notre projet. Ces espaces de noms donnent accès aux classes et méthodes requises pour manipuler les documents Word avec Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Étape 1 : initialiser le document

Tout d’abord, initialisons un nouveau document Word. Considérez cela comme la création d'une toile vierge sur laquelle nous ajouterons les formes de notre groupe.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.EnsureMinimum();
```

 Ici,`EnsureMinimum()` ajoute un ensemble minimal de nœuds requis pour le document.

## Étape 2 : Créer l'objet GroupShape

 Ensuite, nous devons créer un`GroupShape`objet. Cet objet servira de conteneur à d'autres formes, nous permettant de les regrouper.

```csharp
GroupShape groupShape = new GroupShape(doc);
```

## Étape 3 : ajouter des formes au GroupShape

 Maintenant, ajoutons des formes individuelles à notre`GroupShape` récipient. Nous commencerons par une forme de bordure d’accent, puis ajouterons une forme de bouton d’action.

### Ajout d'une forme de bordure d'accent

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1)
{
    Width = 100,
    Height = 100
};
groupShape.AppendChild(accentBorderShape);
```

 Cet extrait de code crée une forme de bordure d'accentuation d'une largeur et d'une hauteur de 100 unités et l'ajoute au`GroupShape`.

### Ajout d'une forme de bouton d'action

```csharp
Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

 Ici, nous créons une forme de bouton d'action, la positionnons et l'ajoutons à notre`GroupShape`.

## Étape 4 : Définir les dimensions GroupShape

 Pour garantir que nos formes s'intègrent bien au sein du groupe, nous devons définir les dimensions du`GroupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

 Ceci définit la largeur et la hauteur du`GroupShape` comme 200 unités et définit la taille des coordonnées en conséquence.

## Étape 5 : Insérez le GroupShape dans le document

 Maintenant, insérons notre`GroupShape` dans le document en utilisant`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

`DocumentBuilder` fournit un moyen simple d'ajouter des nœuds, y compris des formes, au document.

## Étape 6 : Enregistrez le document

Enfin, enregistrez le document dans le répertoire spécifié.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

Et voilà ! Votre document avec des formes de groupe est prêt.

## Conclusion

L'ajout de formes de groupe à vos documents Word ne doit pas nécessairement être un processus compliqué. Avec Aspose.Words pour .NET, vous pouvez créer et manipuler facilement des formes, rendant vos documents plus attrayants et fonctionnels. Suivez les étapes décrites dans ce tutoriel et vous deviendrez un pro en un rien de temps !

## FAQ

### Puis-je ajouter plus de deux formes à un GroupShape ?
 Oui, vous pouvez ajouter autant de formes que nécessaire à un`GroupShape` . Utilisez simplement le`AppendChild` méthode pour chaque forme.

### Est-il possible de styliser les formes dans un GroupShape ?
 Absolument! Chaque forme peut être stylisée individuellement à l'aide des propriétés disponibles dans le`Shape` classe.

### Comment positionner le GroupShape dans le document ?
 Vous pouvez positionner le`GroupShape` en définissant son`Left`et`Top` propriétés.

### Puis-je ajouter du texte aux formes dans GroupShape ?
 Oui, vous pouvez ajouter du texte aux formes à l'aide de l'outil`AppendChild` méthode pour ajouter un`Paragraph` contenant`Run` nœuds avec du texte.

### Est-il possible de regrouper des formes de manière dynamique en fonction des entrées de l'utilisateur ?
Oui, vous pouvez créer et regrouper dynamiquement des formes en fonction des entrées de l'utilisateur en ajustant les propriétés et les méthodes en conséquence.
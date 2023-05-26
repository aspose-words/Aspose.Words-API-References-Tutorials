---
title: Convertir la forme en mathématiques de bureau
linktitle: Convertir la forme en mathématiques de bureau
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à convertir des formes en formules mathématiques Office lors du téléchargement de documents avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-loadoptions/convert-shape-to-office-math/
---

Lorsque vous travaillez avec des documents contenant des formes mathématiques dans une application C#, vous devrez peut-être les convertir en formules mathématiques Office pour une meilleure compatibilité et présentation. Avec la bibliothèque Aspose.Words pour .NET, vous pouvez facilement convertir des formes en formules mathématiques Office lors du chargement d'un document. Dans ce guide étape par étape, nous vous expliquerons comment utiliser le code source Aspose.Words pour .NET C# pour charger un document en convertissant des formes en formules mathématiques Office à l'aide de LoadOptions.

## Comprendre la bibliothèque Aspose.Words

Avant de plonger dans le code, il est important de comprendre la bibliothèque Aspose.Words pour .NET. Aspose.Words est une bibliothèque puissante pour créer, éditer, convertir et protéger des documents Word sur différentes plates-formes, y compris .NET. Il offre de nombreuses fonctionnalités pour manipuler des documents, telles que l'insertion de texte, la modification de la mise en forme, l'ajout de sections et bien plus encore.

## Configuration des options de chargement

La première étape consiste à configurer les options de chargement de notre document. Utilisez la classe LoadOptions pour spécifier les paramètres de chargement. Dans notre cas, nous voulons convertir les formes en formules mathématiques Office, nous devons donc définir la propriété ConvertShapeToOfficeMath sur true. Voici comment procéder :

```csharp
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };
```

Nous créons un nouvel objet LoadOptions et définissons la propriété ConvertShapeToOfficeMath sur true pour activer la conversion des formes en formules mathématiques Office lors du chargement du document.

## Chargement de documents avec conversion de formes en formules mathématiques Office

Maintenant que nous avons configuré les options de chargement, nous pouvons charger le document à l'aide de la classe Document et spécifier les options de chargement. Voici un exemple :

```csharp
Document doc = new Document(dataDir + "Office math.docx", loadOptions);
```

Dans cet exemple, nous chargeons le document "Office math.docx" situé dans le répertoire documents en utilisant les options de chargement spécifiées.

## Enregistrement du document

Après avoir chargé le document avec la conversion des formes en formules mathématiques Office, vous pouvez l'enregistrer au format souhaité à l'aide de la méthode Save de la classe Document. Par exemple, pour enregistrer le document au format .docx :

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

Assurez-vous de remplacer "dataDir" par le chemin du répertoire vers vos documents.

### Exemple de code source pour LoadOptions avec la fonctionnalité "Convertir Shape To Office Math" en utilisant Aspose.Words pour .NET

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configuration des options de chargement avec la fonctionnalité "Convert Shape"

  To Office Math"
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };

// Charger le document avec les options spécifiées
Document doc = new Document(dataDir + "Office math.docx", loadOptions);

//Enregistrez le document au format souhaité
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

## Conclusion

Dans ce guide, nous avons expliqué comment charger un document en convertissant des formes en formules mathématiques Office à l'aide de la bibliothèque Aspose.Words pour .NET. En suivant les étapes fournies et en utilisant le code source C# fourni, vous pouvez facilement appliquer cette fonctionnalité dans votre application C#. La conversion de formes en formules mathématiques Office améliore la compatibilité et la présentation des documents contenant des éléments mathématiques.

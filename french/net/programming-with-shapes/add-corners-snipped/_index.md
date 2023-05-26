---
title: Ajouter des coins coupés
linktitle: Ajouter des coins coupés
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à ajouter une forme avec des coins coupés à un document Word à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-shapes/add-corners-snipped/
---

 Ce didacticiel explique comment ajouter une forme avec des coins coupés à un document Word à l'aide de Aspose.Words pour .NET. La forme des coins coupés peut être personnalisée et insérée à l'aide de la`InsertShape` méthode.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et travail avec des documents Word.

## Étape 1 : Configurer le répertoire de documents
 Commencez par configurer le chemin d'accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"`avec le chemin d'accès réel au répertoire où vous souhaitez enregistrer le document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un nouveau document et DocumentBuilder
 Créez une nouvelle instance de`Document` classe et une`DocumentBuilder` objet de travailler avec le document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Insérez la forme coupée des coins
 Utilisez le`InsertShape` méthode de la`DocumentBuilder` objet pour insérer une forme avec des coins coupés. Spécifiez le type de forme (dans ce cas,`ShapeType.TopCornersSnipped`) et indiquez la taille souhaitée pour la forme.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## Étape 4 : Enregistrer le document
 Enregistrez le document dans le répertoire spécifié à l'aide de la`Save` méthode. Indiquez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous le nom "WorkingWithShapes.AddCornersSnipped.docx".

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### Exemple de code source pour Add Corners Snipped en utilisant Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

C'est ça! Vous avez ajouté avec succès une forme de coins coupés à votre document Word à l'aide de Aspose.Words pour .NET.
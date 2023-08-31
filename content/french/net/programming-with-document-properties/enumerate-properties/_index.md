---
title: Énumérer les propriétés
linktitle: Énumérer les propriétés
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour énumérer les propriétés d’un document avec Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-document-properties/enumerate-properties/
---

Dans ce didacticiel, nous vous guiderons à travers le code source C# pour énumérer les propriétés du document avec Aspose.Words pour .NET. Cette fonctionnalité vous permet d'accéder aux propriétés intégrées et personnalisées d'un document.

## Étape 1 : Configuration du projet

Pour commencer, créez un nouveau projet C# dans votre IDE préféré. Assurez-vous que la bibliothèque Aspose.Words for .NET est référencée dans votre projet.

## Étape 2 : Chargement du document

Dans cette étape, nous allons charger le document Word dont nous souhaitons lister les propriétés. Utilisez le code suivant pour charger le document :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin réel du répertoire où se trouve votre document.

## Étape 3 : Énumération des propriétés

Listons maintenant les propriétés du document, à la fois les propriétés intégrées et personnalisées. Utilisez le code suivant :

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
Console.WriteLine("2. Built-in Properties");

foreach(DocumentProperty prop in doc.BuiltInDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);

Console.WriteLine("3. Custom Properties");

foreach(DocumentProperty prop in doc.CustomDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);
```

Ce code affiche le nom du document, puis répertorie les propriétés intégrées et personnalisées affichant leur nom et leur valeur.

### Exemple de code source pour Enumerate Properties à l’aide d’Aspose.Words for .NET

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	
	Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
	Console.WriteLine("2. Built-in Properties");
	
	foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);

	Console.WriteLine("3. Custom Properties");
	
	foreach (DocumentProperty prop in doc.CustomDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
		
```

 Assurez-vous de spécifier le chemin d'accès correct au document dans le champ`dataDir` variable.

Vous avez maintenant appris à énumérer les propriétés d'un document à l'aide d'Aspose.Words for .NET. En suivant le guide étape par étape fourni dans ce didacticiel, vous pouvez facilement accéder et visualiser les propriétés de vos propres documents.


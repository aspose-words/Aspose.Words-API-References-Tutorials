---
title: Configuration du lien vers le contenu
linktitle: Configuration du lien vers le contenu
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour configurer la liaison au contenu d'un document avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-document-properties/configuring-link-to-content/
---

Dans ce didacticiel, nous vous guiderons à travers le code source C # pour configurer la liaison au contenu avec Aspose.Words pour .NET. Cette fonctionnalité vous permet de créer un lien vers un contenu spécifique dans un document.

## Étape 1 : configuration du projet

Pour commencer, créez un nouveau projet C# dans votre IDE préféré. Assurez-vous que la bibliothèque Aspose.Words pour .NET est référencée dans votre projet.

## Étape 2 : Création du document et du constructeur

Dans cette étape, nous allons créer un nouveau document et initialiser le constructeur. Utilisez le code suivant :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Créer un marque-page

Nous allons maintenant créer un signet dans le document. Utilisez le code suivant pour créer un marque-page contenant du texte :

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

Ce code crée un signet appelé "MyBookmark" et ajoute du texte à l'intérieur.

## Étape 4 : Configurer le lien de contenu

Nous allons maintenant configurer le lien vers le contenu en utilisant les propriétés du document. Utilisez le code suivant pour ajouter et récupérer le lien vers le contenu :

```csharp
// Obtenez la liste de toutes les propriétés personnalisées du document.
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
// Ajoutez une propriété liée au contenu.
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

Ce code ajoute une propriété liée au contenu appelée "Bookmark" avec le signet "MyBookmark". Ensuite, il récupère les informations de propriété liées au contenu telles que l'état du lien, la source du lien et la valeur de la propriété.

### Exemple de code source pour la configuration du lien vers le contenu à l'aide de Aspose.Words pour .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// Récupérez une liste de toutes les propriétés de document personnalisées à partir du fichier.
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// Ajouter une propriété liée au contenu.
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

Vous avez maintenant appris à configurer le lien vers le contenu d'un document à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape fourni dans ce didacticiel, vous pouvez facilement créer et configurer des liens vers un contenu spécifique dans vos propres documents.
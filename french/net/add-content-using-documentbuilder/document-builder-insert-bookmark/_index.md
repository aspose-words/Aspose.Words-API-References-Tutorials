---
title: Générateur de documents Insérer un signet
linktitle: Générateur de documents Insérer un signet
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer des signets dans des documents Word à l'aide de DocumentBuilder dans Aspose.Words pour .NET. Guide étape par étape.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/document-builder-insert-bookmark/
---

Dans cet exemple complet, vous apprendrez à insérer des signets dans un document Word à l'aide de la classe DocumentBuilder dans Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure de créer et de gérer des signets dans vos documents.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : créer un nouveau document et DocumentBuilder
Pour commencer, créez un nouveau document à l'aide de la classe Document et initialisez un objet DocumentBuilder :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Insérer un signet
Ensuite, utilisez les méthodes StartBookmark et EndBookmark de la classe DocumentBuilder pour insérer un signet dans le document. Indiquez un nom unique pour le signet en tant que paramètre :

```csharp
builder.StartBookmark("FineBookmark");
builder.Writeln("This is just a fine bookmark.");
builder.EndBookmark("FineBookmark");
```

## Étape 3 : Enregistrer le document
Après avoir inséré le signet, enregistrez le document dans un fichier à l'aide de la méthode Save de la classe Document :

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.DocumentBuilderInsertBookmark.docx");
```

### Exemple de code source pour DocumentBuilder Insérer un signet à l'aide d'Aspose.Words pour .NET
Voici le code source complet pour insérer un signet à l'aide de la classe DocumentBuilder dans Aspose.Words pour .NET :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartBookmark("FineBookmark");
builder.Writeln("This is just a fine bookmark.");
builder.EndBookmark("FineBookmark");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.DocumentBuilderInsertBookmark.docx");
```

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment insérer des signets dans un document Word à l'aide de la classe DocumentBuilder dans Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais créer et gérer des signets dans vos documents.

Les signets sont utiles pour divers scénarios, tels que la navigation dans des documents volumineux, le référencement de sections spécifiques ou la manipulation par programmation de contenu dans des zones marquées d'un signet.

N'oubliez pas d'ajuster le code en fonction de vos besoins spécifiques et de l'améliorer avec des fonctionnalités supplémentaires si nécessaire.


---
title: Créer un nouveau document
linktitle: Créer un nouveau document
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à créer un nouveau document Word et à ajouter du contenu à l'aide d'Aspose.Words pour .NET. Guide étape par étape.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/create-new-document/
---

Dans ce tutoriel étape par étape, vous apprendrez à créer un nouveau document Word à partir de zéro en utilisant Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure de générer un nouveau document et d'y ajouter du contenu à l'aide de la classe DocumentBuilder.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : créer un nouveau document
Pour commencer, créez un nouveau document en utilisant la classe Document :

```csharp
Document doc = new Document();
```

## Étape 2 : ajouter du contenu au document
Ensuite, utilisez un objet DocumentBuilder pour ajouter du contenu au document. Initialisez le DocumentBuilder avec le document nouvellement créé :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");
```

## Étape 3 : Enregistrer le document
Après avoir ajouté le contenu souhaité, enregistrez le document dans un fichier à l'aide de la méthode Save de la classe Document :

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

## Exemple de code source pour la création d'un nouveau document à l'aide de Aspose.Words pour .NET
Voici le code source complet pour créer un nouveau document en utilisant Aspose.Words pour .NET :

```csharp
Document doc = new Document();

// Utilisez un générateur de document pour ajouter du contenu au document.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment créer un nouveau document Word en utilisant Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais générer de nouveaux documents par programmation et leur ajouter du contenu à l'aide de la classe DocumentBuilder.

Vous pouvez désormais créer et personnaliser en toute confiance des documents Word en fonction de vos besoins spécifiques.

### Exemple de code source pour la création d'un nouveau document à l'aide d'Aspose.Words pour .NET :

```csharp
Document doc = new Document();

// Utilisez un générateur de document pour ajouter du contenu au document.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

N'oubliez pas d'ajuster le chemin et le nom du fichier dans le code pour enregistrer le document à l'emplacement souhaité sur votre système.


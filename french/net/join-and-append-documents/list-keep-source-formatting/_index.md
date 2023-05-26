---
title: Liste Conserver la mise en forme de la source
linktitle: Liste Conserver la mise en forme de la source
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment conserver la mise en forme de la liste lors de la jointure et de l'ajout de documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/list-keep-source-formatting/
---

Ce didacticiel vous guidera tout au long du processus d'utilisation de la fonction List Keep Source Formatting d'Aspose.Words pour .NET. Cette fonctionnalité vous permet de joindre et d'ajouter des documents Word tout en préservant la mise en forme source des listes.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1. Aspose.Words pour .NET installé. Vous pouvez le télécharger depuis le site Web d'Aspose ou l'installer via NuGet.
2. Visual Studio ou tout autre environnement de développement C#.

## Étape 1 : Initialiser les répertoires de documents

 Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. Modifier la valeur de la`dataDir` variable au chemin où se trouvent vos documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Chargez les documents source et de destination

 Ensuite, vous devez charger les documents source et de destination à l'aide de Aspose.Words`Document` classe. Mettez à jour les noms de fichiers dans le`Document` constructeur en fonction des noms de vos documents.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Étape 3 : Définissez le document source pour qu'il circule en continu

 Pour vous assurer que le contenu du document source s'écoule en continu lorsqu'il est ajouté au document de destination, vous devez définir le`SectionStart` propriété de la première section du document source pour`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Étape 4 : Ajouter le document source au document de destination

 Maintenant, vous pouvez ajouter le document source au document de destination en utilisant le`AppendDocument` méthode de la`Document` classe. Le`ImportFormatMode.KeepSourceFormatting`Le paramètre garantit que la mise en forme source, y compris la mise en forme des listes, est préservée pendant l'opération d'ajout.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Étape 5 : Enregistrez le document final

 Enfin, enregistrez le document fusionné avec la fonction List Keep Source Formatting activée à l'aide de la`Save` méthode de la`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### Exemple de code source pour List Keep Source Formatting utilisant Aspose.Words pour .NET 

Voici le code source complet de la fonctionnalité List Keep Source Formatting en C# à l'aide de Aspose.Words pour .NET :

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Ajoutez le contenu du document afin qu'il circule en continu.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

C'est ça! Vous avez implémenté avec succès la fonctionnalité List Keep Source Formatting à l'aide de Aspose.Words pour .NET. Le document final contiendra le contenu fusionné avec la mise en forme de la liste du document source préservée.
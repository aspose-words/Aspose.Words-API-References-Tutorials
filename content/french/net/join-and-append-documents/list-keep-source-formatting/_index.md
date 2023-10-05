---
title: Liste Conserver le formatage source
linktitle: Liste Conserver le formatage source
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment conserver le formatage des listes lors de la jointure et de l'ajout de documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/list-keep-source-formatting/
---

Ce didacticiel vous guidera tout au long du processus d'utilisation de la fonctionnalité List Keep Source Formatting d'Aspose.Words for .NET. Cette fonctionnalité vous permet de joindre et d'ajouter des documents Word tout en préservant la mise en forme source des listes.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1. Aspose.Words pour .NET installé. Vous pouvez le télécharger depuis le site Web Aspose ou l'installer via NuGet.
2. Visual Studio ou tout autre environnement de développement C#.

## Étape 1 : initialiser les répertoires de documents

 Tout d’abord, vous devez définir le chemin d’accès à votre répertoire de documents. Modifier la valeur du`dataDir` variable au chemin où se trouvent vos documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Charger les documents source et de destination

 Ensuite, vous devez charger les documents source et de destination à l'aide du Aspose.Words`Document` classe. Mettez à jour les noms de fichiers dans le`Document` constructeur en fonction des noms de vos documents.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Étape 3 : Définir le document source pour qu'il circule en continu

 Pour garantir que le contenu du document source circule en continu lorsqu'il est ajouté au document de destination, vous devez définir le`SectionStart` propriété de la première section du document source à`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Étape 4 : ajouter le document source au document de destination

 Maintenant, vous pouvez ajouter le document source au document de destination à l'aide du`AppendDocument` méthode du`Document` classe. Le`ImportFormatMode.KeepSourceFormatting`Le paramètre garantit que le formatage source, y compris le formatage des listes, est préservé lors de l’opération d’ajout.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Étape 5 : Enregistrez le document final

 Enfin, enregistrez le document fusionné avec la fonction List Keep Source Formatting activée à l'aide de l'option`Save` méthode du`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### Exemple de code source pour le formatage de la source List Keep à l'aide d'Aspose.Words pour .NET 

Voici le code source complet de la fonctionnalité List Keep Source Formatting en C# à l’aide d’Aspose.Words for .NET :

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Ajoutez le contenu du document pour qu’il circule en continu.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

C'est ça! Vous avez implémenté avec succès la fonctionnalité List Keep Source Formatting à l’aide d’Aspose.Words for .NET. Le document final contiendra le contenu fusionné avec la mise en forme de liste du document source conservée.
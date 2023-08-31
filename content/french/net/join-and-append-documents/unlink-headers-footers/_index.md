---
title: Dissocier les en-têtes et les pieds de page
linktitle: Dissocier les en-têtes et les pieds de page
second_title: API de traitement de documents Aspose.Words
description: Apprenez à joindre et à ajouter des documents Word tout en dissociant les en-têtes et les pieds de page à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/unlink-headers-footers/
---

Ce didacticiel vous guidera tout au long du processus d'utilisation de la fonctionnalité Unlink Headers Footers d'Aspose.Words pour .NET. Cette fonctionnalité vous permet de joindre et d'ajouter des documents Word tout en dissociant les en-têtes et les pieds de page du document source.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1. Aspose.Words pour .NET installé. Vous pouvez le télécharger depuis le site Web d'Aspose ou l'installer via NuGet.
2. Visual Studio ou tout autre environnement de développement C#.

## Étape 1 : Initialiser les répertoires de documents

 Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. Modifier la valeur de la`dataDir`variable au chemin où se trouvent vos documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Chargez les documents source et de destination

 Ensuite, vous devez charger les documents source et de destination à l'aide de Aspose.Words`Document` classe. Mettez à jour les noms de fichiers dans le`Document` constructeur en fonction des noms de vos documents.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Étape 3 : dissocier les en-têtes et les pieds de page du document source

 Pour dissocier les en-têtes et pieds de page du document source de la continuation des en-têtes et pieds de page du document de destination, vous devez définir le`LinkToPrevious` propriété de la`HeadersFooters` collection dans la première section du document source pour`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Étape 4 : Ajouter le document source au document de destination

 Maintenant, vous pouvez ajouter le document source au document de destination en utilisant le`AppendDocument` méthode de la`Document` classe. Le`ImportFormatMode.KeepSourceFormatting` Le paramètre garantit que la mise en forme de la source est préservée pendant l'opération d'ajout.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Étape 5 : Enregistrez le document final

Enfin, enregistrez le document fusionné avec la fonctionnalité Dissocier les en-têtes et les pieds de page activée à l'aide de la`Save` méthode de la`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### Exemple de code source pour Unlink Headers Footers en utilisant Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité "Unlink Headers Footers" en C# à l'aide d'Aspose.Words pour .NET :

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Dissociez les en-têtes et les pieds de page du document source pour arrêter cela
	// de continuer les en-têtes et pieds de page du document de destination.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

C'est ça! Vous avez implémenté avec succès la fonctionnalité Unlink Headers Footers à l'aide de Aspose.Words pour .NET. Le document final contiendra le contenu fusionné avec les en-têtes et pieds de page du document source dissociés du document de destination.
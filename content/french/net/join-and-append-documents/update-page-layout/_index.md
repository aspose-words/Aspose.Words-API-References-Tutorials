---
title: Mettre à jour la mise en page
linktitle: Mettre à jour la mise en page
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment mettre à jour la mise en page lors de la jointure et de l'ajout de documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/update-page-layout/
---

Ce didacticiel vous guidera tout au long du processus d'utilisation de la fonctionnalité Mettre à jour la mise en page d'Aspose.Words pour .NET. Cette fonctionnalité garantit que la mise en page est correctement mise à jour lors de la jointure et de l'ajout de documents Word.

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
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Étape 3 : Mettre à jour la mise en page du document de destination

 Pour vous assurer que la mise en page est correctement mise à jour avant d'ajouter le document source, vous pouvez appeler le`UpdatePageLayout` méthode sur le document de destination.

```csharp
dstDoc.UpdatePageLayout();
```

## Étape 4 : Ajouter le document source au document de destination

 Maintenant, vous pouvez ajouter le document source au document de destination à l'aide du`AppendDocument` méthode du`Document` classe. Le`ImportFormatMode.KeepSourceFormatting` Le paramètre garantit que le formatage source est préservé pendant l’opération d’ajout.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Étape 5 : mettre à jour à nouveau la mise en page

 Après avoir ajouté le document source, vous devez appeler le`UpdatePageLayout`à nouveau sur le document de destination pour garantir que toutes les modifications apportées après l'opération d'ajout sont reflétées dans la sortie rendue.

```csharp
dstDoc.UpdatePageLayout();
```

## Étape 6 : Enregistrez le document final

 Enfin, enregistrez le document fusionné avec la fonctionnalité Mettre à jour la mise en page activée à l'aide de l'icône`Save` méthode du`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### Exemple de code source pour mettre à jour la mise en page à l'aide d'Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité « Mettre à jour la mise en page » en C# à l'aide d'Aspose.Words pour .NET :

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Si le document de destination est rendu au format PDF, image, etc.
	// ou UpdatePageLayout est appelé avant le document source. Est annexé,
	// alors toutes les modifications apportées après ne seront pas reflétées dans la sortie rendue
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// Pour que les modifications soient mises à jour dans la sortie rendue, UpdatePageLayout doit être appelé à nouveau.
	// S'il n'est pas appelé à nouveau, le document ajouté n'apparaîtra pas dans la sortie du prochain rendu.
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

C'est ça! Vous avez implémenté avec succès la fonctionnalité Mettre à jour la mise en page à l’aide d’Aspose.Words pour .NET. Le document final contiendra le contenu fusionné avec la mise en page correctement mise à jour.
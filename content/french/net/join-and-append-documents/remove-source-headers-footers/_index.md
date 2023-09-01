---
title: Supprimer les pieds de page des en-têtes sources
linktitle: Supprimer les pieds de page des en-têtes sources
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment supprimer les en-têtes et les pieds de page lors de la jonction et de l'ajout de documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/remove-source-headers-footers/
---

Ce didacticiel vous guidera tout au long du processus d'utilisation de la fonctionnalité Supprimer les pieds de page des en-têtes sources d'Aspose.Words pour .NET. Cette fonctionnalité vous permet de joindre et d'ajouter des documents Word tout en supprimant les en-têtes et les pieds de page du document source.

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

## Étape 3 : Supprimer les en-têtes et les pieds de page des sections du document source

 Pour supprimer les en-têtes et les pieds de page de chaque section du document source, vous pouvez parcourir les sections à l'aide d'un`foreach` boucle et appelle le`ClearHeadersFooters` méthode.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## Étape 4 : Désactiver le paramètre « LinkToPrevious » pour les en-têtes et les pieds de page

Même après avoir effacé les en-têtes et pieds de page du document source, il est possible que le paramètre « LinkToPrevious » pour`HeadersFooters` peut encore être réglé. Pour éviter ce comportement, vous devez le définir explicitement sur`false` pour la première section`HeadersFooters` propriété.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Étape 5 : Ajouter le document source au document de destination

 Maintenant, vous pouvez ajouter le document source au document de destination à l'aide du`AppendDocument` méthode du`Document` classe. Le`ImportFormatMode.KeepSourceFormatting` Le paramètre garantit que le formatage source est préservé pendant l’opération d’ajout.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Étape 6 : Enregistrez le document final

 Enfin, enregistrez le document fusionné avec la fonctionnalité Supprimer les en-têtes sources et les pieds de page activée à l'aide de l'option`Save` méthode du`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### Exemple de code source pour supprimer les pieds de page des en-têtes sources à l'aide d'Aspose.Words pour .NET 

Voici le code source complet de la fonctionnalité « Supprimer les pieds de page des en-têtes sources » en C# à l'aide d'Aspose.Words pour .NET :


```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Supprimez les en-têtes et pieds de page de chacune des sections du document source.
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// Même une fois les en-têtes et pieds de page effacés du document source, le paramètre « LinkToPrevious »
	// pour les HeadersFooters peuvent toujours être définis. Les en-têtes et pieds de page continueront alors à partir de la destination.
	// document. Cela doit être défini sur false pour éviter ce comportement.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
C'est ça! Vous avez implémenté avec succès la fonctionnalité Supprimer les pieds de page des en-têtes sources à l’aide d’Aspose.Words pour .NET. Le document final contiendra le contenu fusionné avec les en-têtes et pieds de page supprimés du document source.
---
title: Lier les en-têtes et les pieds de page
linktitle: Lier les en-têtes et les pieds de page
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment lier des en-têtes et des pieds de page lors de la jonction et de l'ajout de documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/link-headers-footers/
---

Ce didacticiel vous guidera tout au long du processus d'utilisation de la fonctionnalité Link Headers Footers d'Aspose.Words for .NET. Cette fonctionnalité vous permet de joindre et d'ajouter plusieurs documents Word tout en liant les en-têtes et pieds de page du document source à la section précédente du document de destination.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1. Aspose.Words pour .NET installé. Vous pouvez le télécharger depuis le site Web Aspose ou l'installer via NuGet.
2. Visual Studio ou tout autre environnement de développement C#.

## Étape 1 : initialiser les répertoires de documents

 Tout d’abord, vous devez définir le chemin d’accès à votre répertoire de documents. Modifier la valeur du`dataDir`variable au chemin où se trouvent vos documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Charger les documents source et de destination

 Ensuite, vous devez charger les documents source et de destination à l'aide du Aspose.Words`Document` classe. Mettez à jour les noms de fichiers dans le`Document` constructeur en fonction des noms de vos documents.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Étape 3 : Configurer le document annexé pour qu'il apparaisse sur une nouvelle page

 Pour garantir que le contenu du document source apparaît sur une nouvelle page du document de destination, vous devez définir le`SectionStart` propriété de la première section du document source à`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Étape 4 : lier les en-têtes et les pieds de page à la section précédente

 Pour lier les en-têtes et pieds de page du document source à la section précédente du document destination, vous pouvez utiliser le`LinkToPrevious` méthode du`HeadersFooters` collection. En passant`true` en tant que paramètre, vous remplacez les en-têtes ou pieds de page existants dans le document source.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## Étape 5 : Ajouter le document source au document de destination

 Maintenant, vous pouvez ajouter le document source au document de destination à l'aide du`AppendDocument` méthode du`Document` classe. Le`ImportFormatMode.KeepSourceFormatting` Le paramètre garantit que le formatage source est préservé pendant l’opération d’ajout.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Étape 6 : Enregistrez le document final

 Enfin, enregistrez le document fusionné avec les en-têtes et pieds de page liés à l'aide du`Save` méthode du`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### Exemple de code source pour les pieds de page des en-têtes de lien utilisant Aspose.Words pour .NET 

Voici le code source complet de la fonctionnalité « Link Headers Footers » en C# utilisant Aspose.Words pour .NET :


```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Définissez le document ajouté pour qu'il apparaisse sur une nouvelle page.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Liez les en-têtes et pieds de page du document source à la section précédente.
	// Cela remplacera tous les en-têtes ou pieds de page déjà trouvés dans le document source.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

C'est ça! Vous avez implémenté avec succès la fonctionnalité Link Headers Footers à l’aide d’Aspose.Words for .NET. Le document final contiendra le contenu fusionné avec les en-têtes et pieds de page du document source liés à la section précédente du document de destination.
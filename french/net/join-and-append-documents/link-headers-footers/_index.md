---
title: Liens En-têtes Pieds de page
linktitle: Liens En-têtes Pieds de page
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à lier des en-têtes et des pieds de page tout en joignant et en ajoutant des documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/link-headers-footers/
---

Ce didacticiel vous guidera tout au long du processus d'utilisation de la fonctionnalité Link Headers Footers d'Aspose.Words pour .NET. Cette fonctionnalité vous permet de joindre et d'ajouter plusieurs documents Word tout en liant les en-têtes et les pieds de page du document source à la section précédente du document de destination.

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
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Étape 3 : Définir le document ajouté pour qu'il apparaisse sur une nouvelle page

Pour vous assurer que le contenu du document source apparaît sur une nouvelle page du document de destination, vous devez définir le`SectionStart` propriété de la première section du document source pour`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Étape 4 : Liez les en-têtes et les pieds de page à la section précédente

 Pour lier les en-têtes et pieds de page du document source à la section précédente du document de destination, vous pouvez utiliser la`LinkToPrevious` méthode de la`HeadersFooters` collection. En passant`true` en tant que paramètre, vous remplacez tous les en-têtes ou pieds de page existants dans le document source.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## Étape 5 : Ajouter le document source au document de destination

 Maintenant, vous pouvez ajouter le document source au document de destination en utilisant le`AppendDocument` méthode de la`Document` classe. Le`ImportFormatMode.KeepSourceFormatting` Le paramètre garantit que la mise en forme de la source est préservée pendant l'opération d'ajout.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Étape 6 : Enregistrez le document final

 Enfin, enregistrez le document fusionné avec les en-têtes et pieds de page liés à l'aide de la`Save` méthode de la`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### Exemple de code source pour Link Headers Footers utilisant Aspose.Words pour .NET 

Voici le code source complet de la fonctionnalité "Link Headers Footers" en C# en utilisant Aspose.Words pour .NET :


```csharp
	// Chemin d'accès à votre répertoire de documents
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

C'est ça! Vous avez implémenté avec succès la fonctionnalité Link Headers Footers à l'aide de Aspose.Words pour .NET. Le document final contiendra le contenu fusionné avec les en-têtes et pieds de page du document source liés à la section précédente dans le document de destination.
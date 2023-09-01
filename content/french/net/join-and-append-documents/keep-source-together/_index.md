---
title: Gardez la source ensemble
linktitle: Gardez la source ensemble
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment utiliser Aspose.Words for .NET pour joindre et ajouter des documents Word tout en conservant le contenu source avec le document de destination.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/keep-source-together/
---

Ce didacticiel vous guidera tout au long du processus d'utilisation de la fonctionnalité Keep Source Together d'Aspose.Words for .NET. Cette fonctionnalité vous permet de joindre et d'ajouter plusieurs documents Word tout en conservant le contenu du document source avec celui du document de destination. 

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

## Étape 3 : Définir le document source pour qu'il apparaisse après le contenu du document de destination

 Pour garantir que le document source apparaisse immédiatement après le contenu du document de destination, vous devez définir le`SectionStart` propriété de la première section du document source à`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Étape 4 : définissez le formatage du paragraphe « Conserver avec le suivant » pour le document source

 Pour conserver les paragraphes du document source ensemble, vous pouvez parcourir chaque paragraphe du document et définir le`KeepWithNext` propriété à`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Étape 5 : Ajouter le document source au document de destination

 Maintenant, vous pouvez ajouter le document source au document de destination à l'aide du`AppendDocument` méthode du`Document` classe. Le`ImportFormatMode.KeepSourceFormatting` Le paramètre garantit que le formatage source est préservé pendant l’opération d’ajout.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Étape 6 : Enregistrez le document final

 Enfin, enregistrez le document fusionné avec la fonctionnalité « Conserver la source ensemble » activée à l'aide de l'option`Save` méthode du`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### Exemple de code source pour Keep Source Together à l'aide d'Aspose.Words pour .NET 

Voici le code source complet de la fonctionnalité « Keep Source Together » en C# à l'aide d'Aspose.Words pour .NET :


```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Définissez le document source pour qu'il apparaisse juste après le contenu du document de destination.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

C'est ça! Vous avez implémenté avec succès la fonctionnalité Keep Source Together à l’aide d’Aspose.Words pour .NET. Le document final contiendra le contenu fusionné avec les paragraphes du document source conservés ensemble.
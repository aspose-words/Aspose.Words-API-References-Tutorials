---
title: Avertissements de rendu PDF
linktitle: Avertissements de rendu PDF
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour traiter les avertissements de rendu PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/pdf-render-warnings/
---

Cet article fournit un guide étape par étape sur la façon d'utiliser la fonctionnalité d'avertissements de rendu PDF avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. À la fin de ce didacticiel, vous serez en mesure de comprendre comment gérer les avertissements de rendu lors de la conversion au format PDF.

Avant de commencer, assurez-vous d'avoir installé et configuré la bibliothèque Aspose.Words pour .NET dans votre projet. Vous pouvez trouver la bibliothèque et les instructions d'installation sur le site Web d'Aspose.

## Étape 1 : Définir le répertoire des documents

 Pour commencer, vous devez définir le chemin vers le répertoire où se trouvent vos documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Téléchargez le document

Ensuite, nous devons charger le document que nous voulons traiter. Dans cet exemple, nous supposons que le document s'appelle "WMF avec image.docx" et se trouve dans le répertoire de documents spécifié.

```csharp
Document doc = new Document(dataDir + "WMF with image.docx");
```

## Étape 3 : Configurer les options d'enregistrement au format PDF avec des avertissements de rendu

Pour gérer les avertissements de rendu lors de la conversion au format PDF, nous devons configurer le`MetafileRenderingOptions` object pour spécifier comment les métafichiers sont rendus. Nous utilisons également le`HandleDocumentWarnings` option pour gérer les avertissements générés lors de l'enregistrement du document.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     EmulateRasterOperations = false,
     RenderingMode = MetafileRenderingMode.VectorWithFallback
};

PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
```

## Étape 4 : Enregistrer le document au format PDF avec des avertissements de rendu

Enfin, nous pouvons enregistrer le document au format PDF en utilisant les options d'enregistrement configurées précédemment.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);
```

## Étape 5 : Gérer les avertissements de rendu

Les avertissements de rendu générés lors de l'enregistrement du document peuvent être récupérés à l'aide du gestionnaire d'avertissement personnalisé. Dans cet exemple, nous imprimons simplement la description de chaque avertissement.

```csharp
foreach(WarningInfo warningInfo in callback.mWarnings)
{
     Console.WriteLine(warningInfo.Description);
}
```

C'est tout ! Vous avez géré avec succès les avertissements de rendu lors de la conversion d'un document

  au format PDF en utilisant Aspose.Words pour .NET.

### Exemple de code source pour les avertissements de rendu PDF avec Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with image.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		EmulateRasterOperations = false, RenderingMode = MetafileRenderingMode.VectorWithFallback
	};

	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	// Si Aspose.Words ne peut pas restituer correctement certains des enregistrements de métafichier
	// aux graphiques vectoriels, Aspose.Words rend ce métafichier en bitmap.
	HandleDocumentWarnings callback = new HandleDocumentWarnings();
	doc.WarningCallback = callback;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);

	// Lorsque le fichier est enregistré avec succès, les avertissements de rendu qui se sont produits lors de l'enregistrement sont collectés ici.
	foreach (WarningInfo warningInfo in callback.mWarnings)
	{
		Console.WriteLine(warningInfo.Description);
	}
        
```

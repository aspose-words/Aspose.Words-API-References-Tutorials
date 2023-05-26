---
title: Détecter les signatures de documents
linktitle: Détecter les signatures de documents
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour détecter les signatures numériques dans un document avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-fileformat/detect-document-signatures/
---

Cet article fournit un guide étape par étape sur la façon d'utiliser la fonctionnalité de détection de signature de document avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. A la fin de ce tutoriel, vous serez en mesure de comprendre comment détecter les signatures numériques dans un document.

Avant de commencer, assurez-vous d'avoir installé et configuré la bibliothèque Aspose.Words pour .NET dans votre projet. Vous pouvez trouver la bibliothèque et les instructions d'installation sur le site Web d'Aspose.

## Étape 1 : Définir le répertoire des documents

 Pour commencer, vous devez définir le chemin vers le répertoire où se trouvent vos documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Détecter les signatures numériques

 Ensuite, nous utilisons le`DetectFileFormat` méthode de la`FileFormatUtil` classe pour détecter les informations de format de fichier. Dans cet exemple, nous supposons que le document s'appelle "Digitally signé.docx" et se trouve dans le répertoire de documents spécifié.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");
```

## Étape 3 : Vérifiez les signatures numériques

 Nous vérifions si le document contient des signatures numériques en utilisant le`HasDigitalSignature` propriété de la`FileFormatInfo` objet. Si des signatures numériques sont détectées, nous affichons un message indiquant que les signatures seront perdues si le document est ouvert/enregistré avec Aspose.Words.

```csharp
if (info.HasDigitalSignature)
{
	Console.WriteLine(
		$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
		"they will be lost if you open/save this document with Aspose.Words.");
}
```

C'est tout ! Vous avez détecté avec succès des signatures numériques dans un document à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour détecter les signatures de documents avec Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");

	if (info.HasDigitalSignature)
	{
		Console.WriteLine(
			$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
			"they will be lost if you open/save this document with Aspose.Words.");
	}
	
        
```

---
title: Échapper à Uri
linktitle: Échapper à Uri
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour échapper à Uri avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/escape-uri/
---

Cet article fournit un guide étape par étape sur l'utilisation de la fonctionnalité d'échappement Uri avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. A la fin de ce tutoriel, vous serez en mesure de comprendre comment insérer des liens hypertexte avec Uri échappé dans un document.

Avant de commencer, assurez-vous d'avoir installé et configuré la bibliothèque Aspose.Words pour .NET dans votre projet. Vous pouvez trouver la bibliothèque et les instructions d'installation sur le site Web d'Aspose.

## Étape 1 : Définir le répertoire des documents

 Pour commencer, vous devez définir le chemin vers le répertoire où se trouvent vos documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un document et un DocumentBuilder

 Ensuite, nous devons créer un nouveau`Document` objet et un`DocumentBuilder` objet pour construire le document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Insérer des hyperliens avec Uri échappé

 Utilisez le`InsertHyperlink` méthode de la`DocumentBuilder`object pour insérer des hyperliens dans le document. Uri doit être échappé à l'aide de la`Uri.EscapeUriString` fonction pour éviter les erreurs de format.

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), faux);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), faux);
```

## Étape 4 : Enregistrez le document au format PDF

 Enfin, nous pouvons enregistrer le document au format PDF en utilisant le`Save` méthode de la`Document` objet. Spécifiez le nom du fichier de sortie.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

C'est tout ! Vous avez inséré avec succès des liens hypertexte avec des Uri échappés dans un document à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour Uri s'échappant avec Aspose.Words pour .NET


```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test", faux);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fthe%20test",
		"https://www.google.com/search?q=%2Fthe%20test", faux);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```

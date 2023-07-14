---
title: URI d'échappement dans le document PDF
linktitle: URI d'échappement dans le document PDF
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape Comment échapper l'URI dans un document PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/escape-uri/
---

Cet article fournit un guide étape par étape sur la façon d'échapper l'URI dans un document PDF avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. A la fin de ce tutoriel, vous serez en mesure de comprendre comment insérer des liens hypertexte avec Uri échappé dans un document.

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

 Utilisez le`InsertHyperlink` méthode de la`DocumentBuilder` object pour insérer des hyperliens dans le document. Uri doit être échappé à l'aide de la`Uri.EscapeUriString` fonction pour éviter les erreurs de format.

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

## Conclusion

Dans ce didacticiel, nous avons expliqué comment échapper les URI dans un document PDF à l'aide de Aspose.Words pour .NET. En échappant les URI, vous pouvez éviter les erreurs de formatage et vous assurer que les hyperliens sont correctement interprétés et affichés dans le document PDF. Suivez les étapes décrites pour insérer des hyperliens avec des URI échappés dans votre document PDF. Assurez-vous de vous échapper.

### Questions fréquemment posées

#### Q : Qu'est-ce que l'URI d'échappement dans un document PDF et pourquoi est-ce important ?
: L'URI d'échappement dans un document PDF fait référence à la méthode de conversion des caractères spéciaux d'une URL en séquences d'échappement pour éviter les erreurs de format. Ceci est important car les caractères spéciaux dans une URL peuvent perturber la structure de l'URL et entraîner une mauvaise interprétation ou un rendu incorrect. En échappant les caractères spéciaux, nous garantissons que l'URL est correctement interprétée et affichée dans le document PDF.

#### Q : Comment puis-je utiliser Aspose.Words pour .NET pour échapper les URI dans un document PDF ?
R : Pour échapper les URI dans un document PDF à l'aide d'Aspose.Words pour .NET, suivez ces étapes :

 Définissez le chemin du répertoire où se trouvent vos documents en remplaçant`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel de votre répertoire de documents.

 Créez une nouvelle instance de`Document` classe et une`DocumentBuilder` objet pour construire le document.

 Utilisez le`InsertHyperlink` méthode de la`DocumentBuilder` object pour insérer des hyperliens dans le document. Assurez-vous d'échapper l'URI en utilisant le`Uri.EscapeUriString` fonction pour éviter les erreurs de format.

 Utilisez le`Save` méthode de la`Document` objet pour enregistrer le document au format PDF en précisant le nom du fichier de sortie.

#### Q : Quels sont les avantages d'échapper les URI dans un document PDF ?
R : Les avantages de l'échappement d'URI dans un document PDF sont :

Prévention des erreurs de format : l'échappement d'URI permet d'éviter les erreurs de format causées par des caractères spéciaux dans une URL, garantissant que l'URL est correctement interprétée et affichée dans le document PDF.

Compatibilité avec les lecteurs PDF : les URI échappés sont généralement bien pris en charge par les lecteurs PDF, ce qui garantit une meilleure compatibilité et une expérience utilisateur cohérente.

#### Q : Quels caractères spéciaux doivent être échappés dans un URI ?
 R : Les caractères spéciaux qui doivent être échappés dans un URI sont : espace, <, >, ", #, %, {, },|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.
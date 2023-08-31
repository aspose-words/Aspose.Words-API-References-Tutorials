---
title: Échapper à l'URI dans un document PDF
linktitle: Échapper à l'URI dans un document PDF
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape Comment échapper à l'URI dans un document PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/escape-uri/
---

Cet article fournit un guide étape par étape sur la façon d'échapper à l'URI dans un document PDF avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. A la fin de ce tutoriel, vous pourrez comprendre comment insérer des hyperliens avec Uri échappé dans un document.

Avant de commencer, assurez-vous d'avoir installé et configuré la bibliothèque Aspose.Words for .NET dans votre projet. Vous pouvez trouver la bibliothèque et les instructions d'installation sur le site Web d'Aspose.

## Étape 1 : Définir le répertoire des documents

 Pour commencer, vous devez définir le chemin d’accès au répertoire où se trouvent vos documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un document et un DocumentBuilder

 Ensuite, nous devons créer un nouveau`Document` objet et un`DocumentBuilder` objet pour construire le document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Insérez des hyperliens avec un Uri échappé

 Utilisez le`InsertHyperlink` méthode du`DocumentBuilder` objet pour insérer des hyperliens dans le document. Uri doit être échappé en utilisant le`Uri.EscapeUriString` fonction pour éviter les erreurs de format.

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), faux);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), faux);
```

## Étape 4 : Enregistrez le document au format PDF

 Enfin, nous pouvons enregistrer le document au format PDF en utilisant le`Save` méthode du`Document` objet. Spécifiez le nom du fichier de sortie.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

C'est tout ! Vous avez inséré avec succès des liens hypertexte avec des Uri échappés dans un document à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour l'échappement d'Uri avec Aspose.Words for .NET


```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test", false);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fthe%20test",
		"https://www.google.com/search?q=%2Fthe%20test", false);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment échapper aux URI dans un document PDF à l'aide d'Aspose.Words pour .NET. En échappant aux URI, vous pouvez éviter les erreurs de formatage et garantir que les hyperliens sont correctement interprétés et affichés dans le document PDF. Suivez les étapes décrites pour insérer des hyperliens avec des URI échappés dans votre document PDF. Assurez-vous de vous échapper.

### Questions fréquemment posées

#### Q : Qu'est-ce que l'URI d'échappement dans un document PDF et pourquoi est-il important ?
R : L'URI d'échappement dans un document PDF fait référence à la méthode de conversion des caractères spéciaux d'une URL en séquences d'échappement pour éviter les erreurs de format. Ceci est important car les caractères spéciaux dans une URL peuvent perturber la structure de l'URL et conduire à une mauvaise interprétation ou à un rendu incorrect. En échappant les caractères spéciaux, nous garantissons que l'URL est correctement interprétée et affichée dans le document PDF.

#### Q : Comment puis-je utiliser Aspose.Words for .NET pour échapper aux URI dans un document PDF ?
R : Pour échapper aux URI dans un document PDF à l'aide d'Aspose.Words for .NET, procédez comme suit :

 Définissez le chemin du répertoire où se trouvent vos documents en remplaçant`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel de votre répertoire de documents.

 Créez une nouvelle instance du`Document` classe et un`DocumentBuilder` objet pour construire le document.

 Utilisez le`InsertHyperlink` méthode du`DocumentBuilder` objet pour insérer des hyperliens dans le document. Assurez-vous d'échapper à l'URI en utilisant le`Uri.EscapeUriString` fonction pour éviter les erreurs de format.

 Utilisez le`Save` méthode du`Document` objet pour enregistrer le document au format PDF en précisant le nom du fichier de sortie.

#### Q : Quels sont les avantages de l'échappement des URI dans un document PDF ?
R : Les avantages de l'échappement d'URI dans un document PDF sont :

Prévention des erreurs de format : l'échappement d'URI permet d'éviter les erreurs de format causées par des caractères spéciaux dans une URL, garantissant ainsi que l'URL est correctement interprétée et affichée dans le document PDF.

Compatibilité avec les lecteurs PDF : les URI avec échappement sont généralement bien pris en charge par les lecteurs PDF, garantissant une meilleure compatibilité et une expérience utilisateur cohérente.

#### Q : Quels caractères spéciaux doivent être échappés dans un URI ?
 R : Les caractères spéciaux qui doivent être échappés dans un URI sont : espace, <, >, ", #, %, {, },|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.
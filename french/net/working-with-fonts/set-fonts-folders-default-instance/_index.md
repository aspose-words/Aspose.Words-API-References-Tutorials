---
title: Définir l'instance par défaut des dossiers de polices
linktitle: Définir l'instance par défaut des dossiers de polices
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour définir le dossier de polices par défaut lors du rendu d'un document à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/set-fonts-folders-default-instance/
---

Dans ce didacticiel, nous vous expliquerons étape par étape le processus de définition du dossier de polices par défaut lors du rendu d'un document à l'aide de Aspose.Words pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment définir le dossier de polices par défaut à utiliser lors du rendu de vos documents à l'aide d'Aspose.Words pour .NET.

## Étape 1 : Définir le répertoire des documents
Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. Il s'agit de l'emplacement où vous souhaitez enregistrer votre document rendu modifié. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Définir le dossier de polices par défaut
 Ensuite, vous pouvez définir le dossier de polices par défaut à l'aide de la`FontSettings.DefaultInstance` classe et la`SetFontsFolder()` méthode. Spécifiez le chemin d'accès au dossier des polices que vous souhaitez utiliser comme dossier par défaut.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## Étape 3 : Chargez le document à afficher
 Vous pouvez maintenant charger le document à rendre à l'aide de la commande`Document` classe. Assurez-vous de spécifier le bon chemin d'accès au document.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Étape 4 : Enregistrer le document rendu
 Enfin, vous pouvez enregistrer le document rendu dans un fichier à l'aide de la`Save()` méthode de la`Document` classe. Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### Exemple de code source pour l'instance par défaut de Set Fonts Folders à l'aide de Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
	Document doc = new Document(dataDir + "Rendering.docx");
	doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## Conclusion
Dans ce didacticiel, nous avons appris à définir le dossier de polices par défaut lors du rendu d'un document à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape, vous pouvez facilement spécifier le dossier de polices à utiliser comme dossier par défaut lors du rendu de vos documents. Aspose.Words offre une API puissante et flexible pour travailler avec les polices dans vos documents. Grâce à ces connaissances, vous pouvez contrôler et personnaliser les sources de polices utilisées lors du rendu de vos documents selon vos besoins spécifiques.
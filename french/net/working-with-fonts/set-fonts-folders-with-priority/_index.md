---
title: Définir les dossiers de polices avec priorité
linktitle: Définir les dossiers de polices avec priorité
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour définir les dossiers de polices avec priorité lors du rendu d'un document à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/set-fonts-folders-with-priority/
---

Dans ce didacticiel, nous vous expliquerons étape par étape le processus de définition des dossiers de polices prioritaires lors du rendu d'un document à l'aide de Aspose.Words pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment spécifier plusieurs dossiers de polices avec une priorité de recherche personnalisée lors du rendu de vos documents à l'aide d'Aspose.Words pour .NET.

## Étape 1 : Définir le répertoire des documents
Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. Il s'agit de l'emplacement où vous souhaitez enregistrer votre document rendu modifié. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Définir les dossiers de polices avec priorité
 Ensuite, vous pouvez définir les dossiers de polices avec priorité à l'aide de la`FontSettings` classe et la`SetFontsSources()` méthode. Vous pouvez spécifier plusieurs sources de polices à l'aide d'instances de`SystemFontSource` et`FolderFontSource`. Dans cet exemple, nous avons défini deux sources de polices : la source de polices système par défaut et un dossier de polices personnalisé avec une priorité de 1.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## Étape 3 : Chargez le document à afficher
 Vous pouvez maintenant charger le document à rendre à l'aide de la commande`Document` classe. Assurez-vous de spécifier le bon chemin d'accès au document.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Étape 4 : Enregistrer le document rendu
 Enfin, vous pouvez enregistrer le document rendu dans un fichier à l'aide de la`Save()` méthode de la`Document` classe. Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### Exemple de code source pour Définir les dossiers de polices avec priorité à l'aide de Aspose.Words pour .NET 
```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{
		new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
	});
	Document doc = new Document(dataDir + "Rendering.docx");
	doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## Conclusion
Dans ce didacticiel, nous avons appris à définir des dossiers de polices prioritaires lors du rendu d'un document à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape, vous pouvez facilement spécifier plusieurs dossiers de polices avec une priorité de recherche personnalisée lors du rendu de vos documents. Aspose.Words offre une API puissante et flexible pour travailler avec les polices dans vos documents. Grâce à ces connaissances, vous pouvez contrôler et personnaliser les sources de polices utilisées lors du rendu de vos documents selon vos besoins spécifiques.
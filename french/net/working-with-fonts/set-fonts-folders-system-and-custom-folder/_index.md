---
title: Définir le système de dossiers de polices et le dossier personnalisé
linktitle: Définir le système de dossiers de polices et le dossier personnalisé
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour la configuration des dossiers de polices système et personnalisées lors du rendu d'un document à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

Dans ce didacticiel, nous vous expliquerons étape par étape le processus de définition des dossiers de polices système et d'un dossier personnalisé lors du rendu d'un document à l'aide de Aspose.Words pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment spécifier plusieurs dossiers de polices, y compris le dossier système et un dossier personnalisé, à utiliser lors du rendu de vos documents à l'aide de Aspose.Words pour .NET.

## Étape 1 : Définir le répertoire des documents
Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. Il s'agit de l'emplacement où vous souhaitez enregistrer votre document rendu modifié. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Chargez le document à afficher
 Ensuite, vous pouvez charger le document à rendre à l'aide de la`Document` classe. Assurez-vous de spécifier le bon chemin d'accès au document.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Étape 3 : Définir les dossiers de polices système et personnalisées
 Vous pouvez maintenant définir des dossiers de polices système et un dossier personnalisé à l'aide de la`FontSettings` classe et la`SetFontsSources()` méthode. Tout d'abord, vous devez récupérer la liste des sources de polices dépendantes de l'environnement à l'aide de`GetFontsSources()` et stockez-le dans une liste. Ensuite, vous pouvez créer une nouvelle instance de`FolderFontSource`en spécifiant le chemin d'accès au dossier personnalisé contenant vos polices. Ajoutez cette instance à la liste des sources de polices existantes. Enfin, utilisez`SetFontsSources()` pour mettre à jour les sources de polices avec la nouvelle liste.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Étape 4 : Appliquer les paramètres de police
 Ensuite, vous devez appliquer les paramètres de police à votre document à l'aide de la`FontSettings` propriété de la`Document` classe.

```csharp
doc.FontSettings = fontSettings;
```

## Étape 5 : Enregistrer le document rendu
Enfin, vous pouvez enregistrer le document rendu dans un fichier en

   en utilisant le`Save()` méthode de la`Document` classe. Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### Exemple de code source pour le système de dossiers Set Fonts et le dossier personnalisé à l'aide de Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Rendering.docx");
	FontSettings fontSettings = new FontSettings();
	// Récupérez le tableau des sources de polices dépendant de l'environnement qui sont recherchées par défaut.
	// Par exemple, cela contiendra une source "Windows\Fonts\" sur une machine Windows.
	// Nous ajoutons ce tableau à une nouvelle liste pour faciliter l'ajout ou la suppression d'entrées de police.
	List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
	// Ajoutez une nouvelle source de dossier qui demandera à Aspose.Words de rechercher les polices dans le dossier suivant.
	FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
	// Ajoutez le dossier personnalisé qui contient nos polices à la liste des sources de polices existantes.
	fontSources.Add(folderFontSource);
	FontSourceBase[] updatedFontSources = fontSources.ToArray();
	fontSettings.SetFontsSources(updatedFontSources);
	doc.FontSettings = fontSettings;
	doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Conclusion
Dans ce didacticiel, nous avons appris à définir des dossiers de polices système et un dossier personnalisé lors du rendu d'un document à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape, vous pouvez facilement spécifier plusieurs dossiers de polices, y compris le dossier système et un dossier personnalisé, à utiliser lors du rendu de vos documents. Aspose.Words offre une API puissante et flexible pour travailler avec les polices dans vos documents. Grâce à ces connaissances, vous pouvez contrôler et personnaliser les sources de polices utilisées lors du rendu de vos documents selon vos besoins spécifiques.
---
title: Définir les dossiers de polices Dossiers multiples
linktitle: Définir les dossiers de polices Dossiers multiples
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour définir plusieurs dossiers de polices lors du rendu d'un document à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

Dans ce didacticiel, nous vous expliquerons étape par étape le processus de définition de plusieurs dossiers de polices lors du rendu d'un document à l'aide de Aspose.Words pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment spécifier plusieurs dossiers de polices à utiliser lors du rendu de vos documents à l'aide d'Aspose.Words pour .NET.

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

## Étape 3 : Définir les dossiers de polices
 Vous pouvez maintenant définir plusieurs dossiers de polices à l'aide de la`FontSettings` classe et la`SetFontsFolders()` méthode. Vous pouvez spécifier les chemins d'accès aux dossiers de polices que vous souhaitez utiliser dans un tableau. Dans cet exemple, nous avons spécifié deux dossiers de polices : "C:\MyFonts\" et "D:\Divers\Polices\".

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## Étape 4 : Appliquer les paramètres de police
 Ensuite, vous devez appliquer les paramètres de police à votre document à l'aide de la`FontSettings` propriété de la`Document` classe.

```csharp
doc.FontSettings = fontSettings;
```

## Étape 5 : Enregistrer le document rendu
 Enfin, vous pouvez enregistrer le document rendu dans un fichier à l'aide de la`Save()` méthode de la`Document` classe. Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### Exemple de code source pour Set Fonts Folders Multiple Folders utilisant Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Rendering.docx");
	FontSettings fontSettings = new FontSettings();
	// Notez que ce paramètre remplacera toutes les sources de polices par défaut qui sont recherchées par défaut. Désormais, seuls ces dossiers seront recherchés
	// polices lors du rendu ou de l'incorporation de polices. Pour ajouter une source de police supplémentaire tout en conservant les sources de police système, utilisez à la fois FontSettings.GetFontSources et
	// FontSettings.SetFontSources à la place.
	fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
	doc.FontSettings = fontSettings;
	doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## Conclusion
Dans ce didacticiel, nous avons appris à définir plusieurs dossiers de polices lors du rendu d'un document à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape, vous pouvez facilement spécifier plusieurs dossiers de polices à utiliser lors du rendu de vos documents. Aspose.Words offre une API puissante et flexible pour travailler avec les polices dans vos documents. Grâce à ces connaissances, vous pouvez contrôler et personnaliser les sources de polices utilisées lors du rendu de vos documents selon vos besoins spécifiques.
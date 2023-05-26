---
title: Spécifier la police par défaut lors du rendu
linktitle: Spécifier la police par défaut lors du rendu
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour spécifier la police par défaut lors du rendu d'un document à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/specify-default-font-when-rendering/
---

Dans ce didacticiel, nous vous expliquerons étape par étape le processus de spécification de la police par défaut lors du rendu d'un document à l'aide de Aspose.Words pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment spécifier une police par défaut à utiliser lors du rendu de vos documents à l'aide de Aspose.Words pour .NET.

## Étape 1 : Définir le répertoire des documents
Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. Il s'agit de l'emplacement où vous souhaitez enregistrer votre document rendu modifié. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Chargez le document à afficher
 Ensuite, vous devez charger le document à rendre à l'aide de la`Document` classe. Assurez-vous de spécifier le bon chemin d'accès au document.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Étape 3 : Définir la police par défaut
 Vous pouvez désormais spécifier la police par défaut à utiliser lors du rendu en créant une instance de`FontSettings` classe et la définition de la`DefaultFontName` propriété de la`DefaultFontSubstitution` s'opposer à la`DefaultFontSubstitution` objet`SubstitutionSettings` de`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## Étape 4 : Enregistrer le document rendu
 Enfin, vous pouvez enregistrer le document rendu dans un fichier à l'aide de la`Save()` méthode de la`Document` classe. Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### Exemple de code source pour Spécifier la police par défaut lors du rendu à l'aide de Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Rendering.docx");
	FontSettings fontSettings = new FontSettings();
	// Si la police par défaut définie ici ne peut pas être trouvée lors du rendu, alors
	// la police la plus proche sur la machine est utilisée à la place.
	fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
	doc.FontSettings = fontSettings;
	doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## Conclusion
Dans ce didacticiel, nous avons appris à spécifier la police par défaut lors du rendu d'un document à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape, vous pouvez facilement définir une police par défaut à utiliser lors du rendu de vos documents. Aspose.Words offre une API puissante et flexible pour travailler avec les polices dans vos documents. Grâce à ces connaissances, vous pouvez contrôler et personnaliser le rendu de vos documents en fonction de vos besoins spécifiques.
---
title: Charger les paramètres de secours de Noto
linktitle: Charger les paramètres de secours de Noto
second_title: Référence de l'API Aspose.Words pour .NET
description: Dans ce didacticiel, découvrez comment charger les paramètres de remplacement Noto dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/load-noto-fallback-settings/
---
Dans ce didacticiel, nous vous expliquerons comment charger les paramètres de substitution de police Noto dans un document Word à l'aide de la bibliothèque Aspose.Words pour .NET. Les paramètres Noto Font Substitution vous permettent de gérer la substitution des polices lors de l'affichage ou de l'impression de documents. Nous vous guiderons étape par étape pour vous aider à comprendre et à implémenter le code dans votre projet .NET.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Une connaissance pratique du langage de programmation C#
- La bibliothèque Aspose.Words pour .NET installée dans votre projet

## Étape 1 : Définir le répertoire des documents
 Tout d'abord, vous devez définir le chemin du répertoire vers l'emplacement de votre document Word. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin approprié.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Chargez le document et configurez les paramètres de substitution de police
 Ensuite, nous allons charger le document en utilisant le`Document` classe et configurez les paramètres de remplacement de police à l'aide de la`FontSettings` classe. Nous allons charger les paramètres de secours de la police Noto à l'aide de la`LoadNotoFallbackSettings()` méthode.

```csharp
// Charger le document et configurer les paramètres de substitution de police
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.LoadNotoFallbackSettings();
doc.FontSettings = fontSettings;
```

## Étape 3 : Enregistrez le document
Enfin, nous enregistrerons le document avec les paramètres de substitution de police Noto appliqués.

```csharp
// Enregistrer le document
doc.Save(dataDir + "WorkingWithFonts.NotoFallbackSettings.pdf");
```


### Exemple de code source pour les paramètres de secours Noto à l'aide d'Aspose.Words pour .NET 
```csharp

// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.LoadNotoFallbackSettings();
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.NotoFallbackSettings.pdf");

```

## Conclusion
Dans ce didacticiel, nous avons vu comment charger les paramètres de substitution de police Noto dans un document Word avec Aspose.Words pour .NET. Les paramètres de substitution des polices de Noto vous permettent de gérer la substitution des polices pour améliorer l'affichage et l'impression de vos documents. N'hésitez pas à utiliser cette fonctionnalité pour personnaliser la substitution de polices selon vos besoins.
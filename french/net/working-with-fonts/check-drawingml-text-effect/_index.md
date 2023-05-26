---
title: Vérifier l'effet de texte DrawingML
linktitle: Vérifier l'effet de texte DrawingML
second_title: Référence de l'API Aspose.Words pour .NET
description: Dans ce didacticiel, découvrez comment vérifier les effets de texte DrawingML dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/check-drawingml-text-effect/
---

Dans ce didacticiel, nous vous expliquerons comment vérifier les effets de texte DrawingML dans un document Word à l'aide de la bibliothèque Aspose.Words pour .NET. La vérification des effets de texte DrawingML vous permet de déterminer si un effet spécifique est appliqué à une partie du texte. Nous vous guiderons étape par étape pour vous aider à comprendre et à implémenter le code dans votre projet .NET.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Une connaissance pratique du langage de programmation C#
- La bibliothèque Aspose.Words pour .NET installée dans votre projet
- Un document Word contenant des effets de texte DrawingML

## Étape 1 : Définir le répertoire des documents
 Tout d'abord, vous devez définir le chemin du répertoire vers l'emplacement de votre document Word. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin approprié.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Chargez le document et vérifiez les effets de texte
Ensuite, nous allons charger le document Word et accéder à la collection d'exécutions (séquences de caractères) dans le premier paragraphe du corps du document. Ensuite, nous vérifierons si des effets de texte DrawingML spécifiques sont appliqués à la police de la première exécution.

```csharp
//Charger le document
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Vérifier les effets de texte DrawingML
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### Exemple de code source pour vérifier l'effet DMLText à l'aide d'Aspose.Words pour .NET 

```csharp

// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Une exécution peut avoir plusieurs effets de texte DML appliqués.
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## Conclusion
Dans ce didacticiel, nous avons vu comment vérifier les effets de texte DrawingML dans un document Word à l'aide de Aspose.Words pour .NET. La vérification des effets de texte DrawingML vous permet d'identifier les parties de texte auxquelles des effets spécifiques ont été appliqués. N'hésitez pas à utiliser cette fonctionnalité pour manipuler et analyser les effets de texte dans vos documents Word.

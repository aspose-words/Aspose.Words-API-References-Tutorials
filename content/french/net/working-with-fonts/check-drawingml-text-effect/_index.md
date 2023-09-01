---
title: Vérifier l'effet de texte DrawingML
linktitle: Vérifier l'effet de texte DrawingML
second_title: API de traitement de documents Aspose.Words
description: Dans ce didacticiel, découvrez comment vérifier les effets de texte DrawingML dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/check-drawingml-text-effect/
---

Dans ce didacticiel, nous vous expliquerons comment vérifier les effets de texte DrawingML dans un document Word à l'aide de la bibliothèque Aspose.Words pour .NET. La vérification des effets de texte DrawingML vous permet de déterminer si un effet spécifique est appliqué à une partie du texte. Nous vous guiderons étape par étape pour vous aider à comprendre et à implémenter le code dans votre projet .NET.

## Conditions préalables
Avant de commencer, assurez-vous de disposer des éléments suivants :
- Une connaissance pratique du langage de programmation C#
- La bibliothèque Aspose.Words pour .NET installée dans votre projet
- Un document Word contenant des effets de texte DrawingML

## Étape 1 : Définir le répertoire des documents
 Tout d’abord, vous devez définir le chemin du répertoire vers l’emplacement de votre document Word. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin approprié.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Chargez le document et vérifiez les effets de texte
Ensuite, nous allons charger le document Word et accéder à la collection de séquences (séquences de caractères) dans le premier paragraphe du corps du document. Ensuite, nous vérifierons si des effets de texte DrawingML spécifiques sont appliqués à la police de la première exécution.

```csharp
// Charger le document
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

// Une exécution peut avoir plusieurs effets de texte Dml appliqués.
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## Conclusion
Dans ce didacticiel, nous avons vu comment vérifier les effets de texte DrawingML dans un document Word à l'aide d'Aspose.Words pour .NET. La vérification des effets de texte DrawingML vous permet d'identifier les parties de texte auxquelles des effets spécifiques sont appliqués. N'hésitez pas à utiliser cette fonctionnalité pour manipuler et analyser les effets de texte dans vos documents Word.

### FAQ

#### Q : Comment puis-je accéder aux effets de texte DrawingML dans un document Word à l'aide d'Aspose.Words ?

R : Avec Aspose.Words, vous pouvez accéder aux effets de texte DrawingML dans un document Word à l'aide de l'API fournie. Vous pouvez parcourir les éléments de texte et vérifier les propriétés spécifiques des effets de texte, telles que la couleur, la taille, etc.

#### Q : Quels types d’effets de texte DrawingML sont couramment utilisés dans les documents Word ?

R : Les types d'effets de texte DrawingML couramment utilisés dans les documents Word incluent les ombres, les reflets, les lueurs, les dégradés, etc. Ces effets peuvent être appliqués pour améliorer l'apparence et le formatage du texte.

#### Q : Comment puis-je vérifier la couleur d'un effet de texte DrawingML dans un document Word ?

: Pour vérifier la couleur d'un effet de texte DrawingML dans un document Word, vous pouvez utiliser les méthodes fournies par Aspose.Words pour accéder aux propriétés de couleur de l'effet de texte. De cette façon, vous pouvez obtenir la couleur utilisée pour l'effet de texte spécifique.

#### Q : Est-il possible de vérifier les effets de texte dans les documents Word contenant plusieurs sections ?

R : Oui, Aspose.Words permet de vérifier les effets de texte dans les documents Word contenant plusieurs sections. Vous pouvez naviguer dans chaque section du document et accéder aux effets de texte pour chaque section individuellement.

#### Q : Comment puis-je vérifier l'opacité d'un effet de texte DrawingML dans un document Word ?

R : Pour vérifier l'opacité d'un effet de texte DrawingML dans un document Word, vous pouvez utiliser les méthodes fournies par Aspose.Words pour accéder aux propriétés d'opacité de l'effet de texte. Cela vous permettra d'obtenir la valeur d'opacité appliquée à l'effet de texte spécifique.
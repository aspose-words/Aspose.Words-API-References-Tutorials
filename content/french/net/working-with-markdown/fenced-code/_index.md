---
title: Code clôturé
linktitle: Code clôturé
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment ajouter du code isolé et des chaînes d'informations aux documents Word à l'aide d'Aspose.Words pour .NET. Guide étape par étape inclus. Améliorez vos compétences en matière de formatage de documents.
type: docs
weight: 10
url: /fr/net/working-with-markdown/fenced-code/
---
## Introduction

Salut, camarade codeur ! Aujourd'hui, nous plongeons dans le monde d'Aspose.Words pour .NET pour maîtriser l'art de l'ajout de code clôturé et de code clôturé avec des chaînes d'informations à vos documents Word. Imaginez votre document Word comme une toile et vous, l'artiste, êtes sur le point de peindre avec la précision d'un développeur chevronné. Avec Aspose.Words, vous avez le pouvoir d'améliorer par programmation vos documents avec des blocs de code structurés et formatés, faisant ainsi briller vos documents techniques avec professionnalisme et clarté.

## Conditions préalables

Avant de passer au didacticiel, assurons-nous que vous disposez de tout ce dont vous avez besoin :

- Connaissance de base de C# : Une compréhension générale de C# vous aidera à appréhender rapidement les concepts.
-  Aspose.Words pour .NET : vous devez avoir installé Aspose.Words pour .NET. Si vous ne l'avez pas encore, prenez-le[ici](https://releases.aspose.com/words/net/).
- Environnement de développement : Visual Studio ou tout autre IDE C# avec lequel vous êtes à l'aise.

## Importer des espaces de noms

Tout d’abord, vous devez importer les espaces de noms nécessaires. C'est comme rassembler tous vos outils avant de démarrer un projet.

```csharp
using Aspose.Words;
using Aspose.Words.Style;
```

Maintenant, décomposons le processus étape par étape.

## Étape 1 : Configuration de votre projet

Avant de pouvoir créer de superbes blocs de code formatés dans notre document Word, nous devons configurer un nouveau projet dans Visual Studio.

1. Créer un nouveau projet : ouvrez Visual Studio et créez une nouvelle application console C#.
2. Ajouter une référence Aspose.Words : installez Aspose.Words via NuGet Package Manager. Vous pouvez le faire en cliquant avec le bouton droit sur votre projet dans l'Explorateur de solutions, en sélectionnant « Gérer les packages NuGet » et en recherchant Aspose.Words.

## Étape 2 : initialiser DocumentBuilder

Maintenant que votre projet est configuré, initialisons DocumentBuilder, qui sera notre principal outil pour ajouter du contenu au document Word.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 3 : Créer un style pour le code clôturé

Pour ajouter du code clôturé, nous devons d’abord créer un style. Considérez cela comme définissant le thème de notre bloc de code.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
fencedCode.Font.Name = "Courier New";
fencedCode.Font.Size = 10;
fencedCode.ParagraphFormat.LeftIndent = 20;
fencedCode.ParagraphFormat.RightIndent = 20;
fencedCode.ParagraphFormat.Shading.BackgroundPatternColor = Color.LightGray;
```

## Étape 4 : ajouter du code clôturé au document

Notre style étant prêt, nous pouvons maintenant ajouter un bloc de code clôturé au document.

```csharp
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is a fenced code block");
```

## Étape 5 : Créer un style pour le code clôturé avec la chaîne d'informations

Parfois, vous souhaiterez peut-être spécifier le langage de programmation ou ajouter des informations supplémentaires à votre bloc de code. Créons un style pour cela.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
fencedCodeWithInfo.Font.Name = "Courier New";
fencedCodeWithInfo.Font.Size = 10;
fencedCodeWithInfo.ParagraphFormat.LeftIndent = 20;
fencedCodeWithInfo.ParagraphFormat.RightIndent = 20;
fencedCodeWithInfo.ParagraphFormat.Shading.BackgroundPatternColor = Color.LightGray;
```

## Étape 6 : Ajouter un code clôturé avec une chaîne d'informations au document

Maintenant, ajoutons un bloc de code clôturé avec une chaîne d'informations pour indiquer qu'il s'agit de code C#.

```csharp
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code block with info string - C#");
```

## Conclusion

Félicitations! Vous venez d'ajouter des blocs de code clôturés et du code clôturé avec des chaînes d'informations à vos documents Word à l'aide d'Aspose.Words pour .NET. Ce n'est que la pointe de l'iceberg. Avec Aspose.Words, vous pouvez automatiser et améliorer le traitement de vos documents vers de nouveaux sommets. Continuez à explorer et bon codage !

## FAQ

### Qu’est-ce qu’Aspose.Words pour .NET ?
Aspose.Words for .NET est une bibliothèque puissante qui permet aux développeurs de créer, manipuler et convertir des documents Word par programme.

### Puis-je utiliser Aspose.Words avec d’autres langages de programmation ?
Aspose.Words prend principalement en charge les langages .NET, mais des versions sont disponibles pour Java, Python et d'autres langages.

### L’utilisation d’Aspose.Words est-elle gratuite ?
 Aspose.Words est un produit commercial, mais vous pouvez télécharger un essai gratuit[ici](https://releases.aspose.com/)pour découvrir ses fonctionnalités.

### Comment puis-je obtenir de l'aide pour Aspose.Words ?
 Vous pouvez obtenir le soutien de la communauté Aspose et des développeurs[ici](https://forum.aspose.com/c/words/8).

### Quelles autres fonctionnalités Aspose.Words offre-t-il ?
Aspose.Words offre un large éventail de fonctionnalités, notamment la conversion de documents, la génération de documents basés sur des modèles, la création de rapports et bien plus encore.
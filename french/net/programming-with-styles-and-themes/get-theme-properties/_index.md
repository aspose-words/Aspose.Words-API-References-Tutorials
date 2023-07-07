---
title: Obtenir les propriétés du thème
linktitle: Obtenir les propriétés du thème
second_title: Référence de l'API Aspose.Words pour .NET
description: Explorez les propriétés de thème d'un document avec Aspose.Words pour .NET. Personnalisez les styles et les couleurs pour un look unique.
type: docs
weight: 10
url: /fr/net/programming-with-styles-and-themes/get-theme-properties/
---

Dans ce didacticiel, nous allons explorer le code source C # fourni pour obtenir les propriétés de thème d'un document à l'aide de Aspose.Words pour .NET. Les propriétés du thème incluent les polices primaires et secondaires utilisées, ainsi que les couleurs d'accentuation.

## Étape 1 : Configurer l'environnement

Assurez-vous d'avoir configuré votre environnement de développement avec Aspose.Words pour .NET. Assurez-vous d'avoir ajouté les références nécessaires et importé les espaces de noms appropriés.

## Étape 2 : Création d'un objet de document

```csharp
Document doc = new Document();
```

 Dans cette étape, nous créons un nouveau`Document` objet.

## Étape 3 : Obtenir les propriétés du thème

```csharp
Aspose.Words.Themes.Theme theme = doc.Theme;

Console.WriteLine(theme.MajorFonts.Latin);
Console.WriteLine(theme.MinorFonts.EastAsian);
Console.WriteLine(theme.Colors.Accent1);
```

 Dans cette étape, nous utilisons le`Theme` propriété de la`Document`objet pour obtenir le`Theme` objet. Ensuite on peut accéder aux différentes propriétés du thème comme les polices principales (`MajorFonts`), les polices secondaires (`MinorFonts`) et les couleurs d'accentuation (`Colors`).

## Étape 4 : Afficher les propriétés du thème

 Dans cette dernière étape, nous affichons les valeurs des propriétés du thème en utilisant`Console.WriteLine`. Vous pouvez adapter l'affichage en fonction de vos besoins.

Vous pouvez exécuter le code source pour obtenir les propriétés de thème d'un document. Cette fonctionnalité vous permet de récupérer des informations sur les polices et les couleurs utilisées dans le thème d'un document, ce qui peut être utile pour la personnalisation ou l'analyse du style.

### Exemple de code source pour obtenir les propriétés du thème à l'aide d'Aspose.Words pour .NET 
```csharp
 
Document doc = new Document();

Aspose.Words.Themes.Theme theme = doc.Theme;

Console.WriteLine(theme.MajorFonts.Latin);
Console.WriteLine(theme.MinorFonts.EastAsian);
Console.WriteLine(theme.Colors.Accent1);

        
```

## Conclusion

 Dans ce didacticiel, nous avons exploré la fonctionnalité d'obtention des propriétés de thème d'un document avec Aspose.Words pour .NET. En utilisant le`Theme` object et ses propriétés associées, nous avons pu accéder à des informations sur les polices primaires et secondaires ainsi que sur les couleurs d'accent utilisées dans le thème du document.

La possibilité d'obtenir des propriétés de thème vous permet d'analyser et de personnaliser les styles et les mises en page de vos documents. Vous pouvez utiliser ces informations pour appliquer des modifications ciblées, créer des rapports ou effectuer des analyses sur l'utilisation des polices et des couleurs dans vos documents.

Aspose.Words pour .NET offre une API puissante pour manipuler les thèmes de vos documents, vous permettant d'ajuster et de personnaliser facilement l'apparence de vos documents.

N'hésitez pas à explorer plus de fonctionnalités d'Aspose.Words pour .NET pour améliorer votre flux de travail et répondre à vos besoins spécifiques en matière de style et de gestion de thème.
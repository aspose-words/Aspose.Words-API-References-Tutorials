---
title: Rompre un lien
linktitle: Rompre un lien
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à rompre les liens dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-textboxes/break-a-link/
---

Aspose.Words pour .NET est une bibliothèque puissante qui offre diverses fonctionnalités pour travailler avec des documents Microsoft Word par programmation. L'une de ses fonctionnalités utiles est la possibilité de rompre les liens dans un document. Dans ce didacticiel, nous allons explorer le code source en C# qui montre comment rompre un lien à l'aide de Aspose.Words pour .NET.

## Étape 1 : Aperçu du code source C#

Le code source C# fourni se concentre sur la fonctionnalité "Break A Link" d'Aspose.Words pour .NET. Il montre comment rompre un lien dans une forme TextBox à l'intérieur d'un document. Le code présente différents scénarios pour rompre les liens et fournit des instructions claires sur la façon d'obtenir les résultats souhaités.

## Étape 2 : Configuration du document et création d'une forme TextBox

 Pour commencer, nous devons configurer le document et créer une forme TextBox. Le code suivant initialise une nouvelle instance de`Document` classe et crée une forme de zone de texte :

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Étape 3 : Casser le lien vers l'avant dans TextBox

 Pour rompre un lien vers l'avant dans la zone de texte, nous pouvons utiliser le`BreakForwardLink()`méthode. Cette méthode rompt le lien vers la forme suivante dans la séquence. Le code suivant montre comment rompre un lien vers l'avant :

```csharp
textBox.BreakForwardLink();
```

## Étape 4 : Rompre un lien direct en définissant une valeur nulle

 Alternativement, nous pouvons rompre un lien vers l'avant en définissant le TextBox's`Next` propriété à`null`. Cela supprime efficacement la connexion à la forme suivante. Le code suivant illustre cette approche :

```csharp
textBox. Next = null;
```

## Étape 5 : Rompre un lien qui mène à la zone de texte

 Dans certains cas, nous devons rompre un lien qui mène à la forme TextBox. Nous pouvons y parvenir en appelant le`BreakForwardLink()` méthode sur la`Previous` formulaire, qui rompt le lien vers le TextBox. Voici un exemple de la façon de rompre un tel lien :

```csharp
textBox.Previous?.BreakForwardLink();
```

### Exemple de code source pour rompre un lien avec Aspose.Words pour .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

// Casser le lien vers l'avant.
textBox.BreakForwardLink();

// Rompre un lien direct en définissant une valeur nulle.
textBox. Next = null;

// Rompre un lien qui mène à cette zone de texte.
textBox.Previous?.BreakForwardLink();
```


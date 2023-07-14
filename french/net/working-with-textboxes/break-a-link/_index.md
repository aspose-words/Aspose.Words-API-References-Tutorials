---
title: Casser le lien vers l'avant dans le document Word
linktitle: Casser le lien vers l'avant dans le document Word
second_title: API de traitement de documents Aspose.Words
description: Apprenez à rompre les liens vers l'avant dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-textboxes/break-a-link/
---

Aspose.Words pour .NET est une bibliothèque puissante qui offre diverses fonctionnalités pour le traitement de mots avec des documents Microsoft Word par programmation. L'une de ses fonctionnalités utiles est la possibilité de rompre les liens vers l'avant dans un document Word. Dans ce didacticiel, nous allons explorer le code source en C # qui montre comment casser un lien vers l'avant dans un document Word à l'aide de Aspose.Words pour .NET.

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

 Pour rompre un lien vers l'avant dans la zone de texte, nous pouvons utiliser le`BreakForwardLink()` méthode. Cette méthode rompt le lien vers la forme suivante dans la séquence. Le code suivant montre comment rompre un lien vers l'avant :

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

## Conclusion

Félicitation ! Vous avez maintenant appris à rompre les liens de redirection dans un document Word à l'aide de la bibliothèque Aspose.Words pour .NET. En suivant les étapes de ce guide, vous avez pu configurer le document, créer une forme TextBox et rompre les liens de redirection à l'aide de différentes méthodes.

### FAQ pour le lien vers l'avant dans un document Word

#### Q : Quelle est la bibliothèque utilisée pour rompre les liens de redirection dans un document Word à l'aide d'Aspose.Words pour .NET ?

R : Pour rompre les liens de redirection dans un document Word à l'aide d'Aspose.Words pour .NET, la bibliothèque utilisée est Aspose.Words pour .NET.

#### Q : Comment casser un lien de redirection dans une TextBox ?

 R : Pour rompre un lien vers l'avant dans une zone de texte, vous pouvez utiliser le`BreakForwardLink()` méthode. Cette méthode rompt le lien vers la forme suivante dans la séquence.

#### Q : Comment rompre un lien de redirection en définissant une valeur nulle ?

R : Vous pouvez également rompre un lien de redirection en définissant le`Next` propriété du TextBox à`null`. Cela supprime efficacement la connexion à la forme suivante.

#### Q : Comment rompre un lien qui mène à la TextBox ?

 R : Dans certains cas, vous devez rompre un lien qui mène à la zone de texte. Vous pouvez y parvenir en appelant le`BreakForwardLink()` méthode sur la`Previous` formulaire, qui rompt le lien vers le TextBox.

#### Q : Pouvons-nous rompre les liens de redirection sur des éléments autres que les zones de texte ?

R : Oui, avec Aspose.Words pour .NET, il est possible de rompre les liens de redirection sur différents éléments tels que des paragraphes, des tableaux, des images, etc. Le processus peut varier en fonction de l'élément spécifique sur lequel vous souhaitez rompre le lien.
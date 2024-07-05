---
title: Rompre le lien suivant dans un document Word
linktitle: Rompre le lien suivant dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment rompre les liens dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-textboxes/break-a-link/
---

Aspose.Words for .NET est une bibliothèque puissante qui offre diverses fonctionnalités pour le traitement de mots avec des documents Microsoft Word par programmation. L'une de ses fonctionnalités utiles est la possibilité de rompre des liens dans un document Word. Dans ce didacticiel, nous explorerons le code source en C# qui montre comment rompre un lien direct dans un document Word à l'aide d'Aspose.Words pour .NET.

## Étape 1 : Aperçu du code source C#

Le code source C# fourni se concentre sur la fonctionnalité « Break A Link » d'Aspose.Words pour .NET. Il montre comment rompre un lien dans une forme TextBox à l'intérieur d'un document. Le code présente différents scénarios de rupture de liens et fournit des instructions claires sur la manière d'obtenir les résultats souhaités.

## Étape 2 : Configuration du document et création d'une forme TextBox

 Pour commencer, nous devons configurer le document et créer une forme TextBox. Le code suivant initialise une nouvelle instance de`Document` classe et crée une forme de zone de texte :

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Étape 3 : Transférer le lien dans TextBox

 Pour rompre un lien direct dans la TextBox, nous pouvons utiliser le`BreakForwardLink()` méthode. Cette méthode rompt le lien vers la forme suivante de la séquence. Le code suivant montre comment rompre un lien direct :

```csharp
textBox.BreakForwardLink();
```

## Étape 4 : rompez un lien direct en définissant une valeur nulle

 Alternativement, nous pouvons rompre un lien direct en définissant le paramètre TextBox`Next`propriété à`null`. Cela supprime efficacement la connexion à la forme suivante. Le code suivant illustre cette approche :

```csharp
textBox. Next = null;
```

## Étape 5 : rompre un lien qui mène à la TextBox

 Dans certains cas, nous devons rompre un lien qui mène à la forme TextBox. Nous pouvons y parvenir en appelant le`BreakForwardLink()` méthode sur le`Previous` formulaire, qui rompt le lien vers le TextBox. Voici un exemple de la manière de rompre un tel lien :

```csharp
textBox.Previous?.BreakForwardLink();
```

### Exemple de code source pour rompre un lien avec Aspose.Words for .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

// Lien vers l'avant.
textBox.BreakForwardLink();

// Rompre un lien direct en définissant une valeur nulle.
textBox. Next = null;

// Rompre un lien qui mène à cette zone de texte.
textBox.Previous?.BreakForwardLink();
```

## Conclusion

Félicitation ! Vous avez maintenant appris à rompre les liens de redirection dans un document Word à l'aide de la bibliothèque Aspose.Words pour .NET. En suivant les étapes de ce guide, vous avez pu configurer le document, créer une forme TextBox et rompre les liens de redirection en utilisant différentes méthodes.

### FAQ pour le lien avancé dans un document Word

#### Q : Quelle est la bibliothèque utilisée pour rompre les liens de redirection dans un document Word à l'aide d'Aspose.Words pour .NET ?

R : Pour rompre les liens de redirection dans un document Word à l'aide d'Aspose.Words for .NET, la bibliothèque utilisée est Aspose.Words for .NET.

#### Q : Comment rompre un lien de redirection dans une TextBox ?

 R : Pour rompre un lien direct dans une TextBox, vous pouvez utiliser le`BreakForwardLink()` méthode. Cette méthode rompt le lien vers la forme suivante de la séquence.

#### Q : Comment rompre un lien de redirection en définissant une valeur nulle ?

R : Vous pouvez également rompre un lien de redirection en définissant le`Next` propriété du TextBox à`null`. Cela supprime efficacement la connexion à la forme suivante.

#### Q : Comment rompre un lien qui mène vers la TextBox ?

 R : Dans certains cas, vous devez rompre un lien qui mène à la TextBox. Vous pouvez y parvenir en appelant le`BreakForwardLink()` méthode sur le`Previous` formulaire, qui rompt le lien vers le TextBox.

#### Q : Pouvons-nous rompre les liens de redirection sur des éléments autres que les TextBox ?

R : Oui, avec Aspose.Words pour .NET, il est possible de rompre les liens de redirection sur différents éléments tels que des paragraphes, des tableaux, des images, etc. Le processus peut varier en fonction de l'élément spécifique sur lequel vous souhaitez rompre le lien.
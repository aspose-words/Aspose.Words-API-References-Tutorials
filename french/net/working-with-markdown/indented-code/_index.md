---
title: Code en retrait
linktitle: Code en retrait
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à utiliser le code indenté avec le guide pas à pas Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/indented-code/
---

Dans cet exemple, nous expliquerons comment utiliser la fonctionnalité de code indenté avec Aspose.Words pour .NET. Le code indenté est utilisé pour représenter visuellement des blocs de code avec une mise en forme spécifique.

## Étape 1 : Utiliser un générateur de documents

Tout d'abord, nous allons utiliser un générateur de document pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : Ajouter un style pour le code en retrait

Nous allons ajouter un style personnalisé pour le code indenté en utilisant le`Styles.Add` méthode de la`Document` objet. Dans cet exemple, nous créons un style appelé "IndentedCode" pour le code indenté.

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## Étape 3 : Ajouter du code en retrait

Nous pouvons maintenant ajouter un bloc de code indenté en utilisant le style personnalisé "IndentedCode".

```csharp
builder.Writeln("This is an indented code block");
```

### Exemple de code source pour le code indenté avec Aspose.Words pour .NET

```csharp
// Utilisez un générateur de document pour ajouter du contenu au document.
DocumentBuilder builder = new DocumentBuilder();

Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
builder.Writeln("This is an indented code");
```

Félicitation ! Vous avez maintenant appris à utiliser la fonctionnalité de code indenté avec Aspose.Words pour .NET.


### FAQ

#### Q : Qu'est-ce que le code indenté dans Markdown ?

R : Le code indenté dans Markdown est une méthode de formatage utilisée pour afficher le code dans un document Markdown. Il consiste à indenter chaque ligne de code avec des espaces ou des tabulations.

#### Q : Comment utiliser le code indenté dans Markdown ?

R : Pour utiliser du code indenté dans Markdown, indentez chaque ligne de code avec des espaces ou des tabulations.

#### Q : Quels sont les avantages du code indenté dans Markdown ?

R : Le code indenté dans Markdown améliore la lisibilité du code et le rend plus facile à comprendre pour les lecteurs.

#### Q : Quelle est la différence entre le code indenté et les blocs de code dans Markdown ?

R : Le code en retrait est utilisé pour les petits extraits de code insérés dans le texte, tandis que les blocs de code sont utilisés pour afficher des morceaux de code plus volumineux dans un formatage séparé.

#### Q : Le code indenté dans Markdown est-il pris en charge par tous les éditeurs Markdown ?

R : La prise en charge du code indenté dans Markdown peut varier d'un éditeur Markdown à l'autre. Vérifiez la documentation spécifique de votre éditeur pour vous en assurer.
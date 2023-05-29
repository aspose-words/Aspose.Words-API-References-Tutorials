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


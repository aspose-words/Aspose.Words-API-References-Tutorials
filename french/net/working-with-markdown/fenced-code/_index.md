---
title: Code clôturé
linktitle: Code clôturé
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à utiliser la fonctionnalité de code clôturé avec Aspose.Words for .NET Guide étape par étape.
type: docs
weight: 10
url: /fr/net/working-with-markdown/fenced-code/
---

Dans cet exemple, nous vous expliquerons comment utiliser la fonctionnalité de code clôturé avec Aspose.Words pour .NET. le code clôturé est utilisé pour représenter des blocs de code avec un formatage spécifique.

## Étape 1 : Utiliser un générateur de documents

Tout d'abord, nous allons utiliser un générateur de document pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : Ajouter un style pour le code clôturé

 Nous allons ajouter un style personnalisé pour le code clôturé en utilisant le`Styles.Add` méthode de la`Document` objet. Dans cet exemple, nous créons un style appelé "FencedCode" pour le code clôturé.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## Étape 3 : Ajouter du code clôturé sans info

Nous pouvons maintenant ajouter un bloc de code clôturé sans chaîne d'informations en utilisant le style personnalisé "FencedCode".

```csharp
builder.Writeln("This is an fenced code");
```

## Étape 4 : Ajouter un code clôturé avec une chaîne d'informations

Nous pouvons également ajouter un bloc de code clôturé avec une chaîne d'informations en utilisant un autre style personnalisé. Dans cet exemple, nous créons un style appelé "FencedCode.C#" pour représenter un bloc de code C#.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Exemple de code source pour le code clôturé utilisant Aspose.Words pour .NET

```csharp
// Utilisez un générateur de document pour ajouter du contenu au document.
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```



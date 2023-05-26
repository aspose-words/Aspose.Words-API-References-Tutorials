---
title: Code en ligne
linktitle: Code en ligne
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à coder en ligne avec le guide étape par étape Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/inline-code/
---

Dans cet exemple, nous vous expliquerons comment utiliser la fonctionnalité de code en ligne avec Aspose.Words pour .NET. Le code en ligne est utilisé pour représenter visuellement des morceaux de code à l'intérieur d'un paragraphe.

## Étape 1 : Utiliser un générateur de documents

Tout d'abord, nous allons utiliser un générateur de document pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : Ajouter un style pour le code en ligne

 Nous allons ajouter un style personnalisé pour le code en ligne en utilisant le`Styles.Add` méthode de la`Document` objet. Dans cet exemple, nous créons un style appelé "InlineCode" pour le code en ligne avec un backtick par défaut.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## Étape 3 : Ajouter du code en ligne

Nous pouvons maintenant ajouter du code en ligne en utilisant le style personnalisé "InlineCode". Dans cet exemple, nous ajoutons deux morceaux de texte avec différents nombres de backticks.

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### Exemple de code source pour le code en ligne avec Aspose.Words pour .NET

```csharp
	// Utilisez un générateur de document pour ajouter du contenu au document.
	DocumentBuilder builder = new DocumentBuilder();

	//Le nombre de backticks est manqué, un backtick sera utilisé par défaut.
	Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
	builder.Font.Style = inlineCode1BackTicks;
	builder.Writeln("Text with InlineCode style with 1 backtick");

	// Il y aura 3 backticks.
	Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
	builder.Font.Style = inlineCode3BackTicks;
	builder.Writeln("Text with InlineCode style with 3 backtick");
            
```

Félicitation ! Vous avez maintenant appris à utiliser la fonctionnalité de code en ligne avec Aspose.Words pour .NET.


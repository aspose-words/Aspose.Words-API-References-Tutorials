---
title: Code en ligne
linktitle: Code en ligne
second_title: API de traitement de documents Aspose.Words
description: Apprenez à intégrer du code avec le guide étape par étape d'Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/inline-code/
---

Dans cet exemple, nous vous expliquerons comment utiliser la fonctionnalité de code en ligne avec Aspose.Words pour .NET. Le code en ligne est utilisé pour représenter visuellement des morceaux de code à l'intérieur d'un paragraphe.

## Étape 1 : Utiliser un générateur de documents

Tout d’abord, nous utiliserons un générateur de documents pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : Ajouter un style pour le code en ligne

 Nous ajouterons un style personnalisé pour le code en ligne en utilisant le`Styles.Add` méthode du`Document` objet. Dans cet exemple, nous créons un style appelé « InlineCode » pour le code en ligne avec un backtick par défaut.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## Étape 3 : ajouter du code en ligne

Nous pouvons maintenant ajouter du code en ligne en utilisant le style personnalisé "InlineCode". Dans cet exemple, nous ajoutons deux morceaux de texte avec des nombres différents de backticks.

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
// Utilisez un générateur de documents pour ajouter du contenu au document.
DocumentBuilder builder = new DocumentBuilder();

// Le nombre de backticks est manqué, un backtick sera utilisé par défaut.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

// Il y aura 3 backticks.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

Félicitation ! Vous avez maintenant appris à utiliser la fonctionnalité de code en ligne avec Aspose.Words pour .NET.


### FAQ

#### Q : Comment puis-je utiliser le code en ligne dans Aspose.Words ?

 R : Pour utiliser du code en ligne dans Aspose.Words, vous pouvez utiliser des balises appropriées pour entourer le texte à formater en code en ligne. Par exemple, vous pouvez utiliser le`<code>` ou`<kbd>` balise pour entourer le texte à formater en code en ligne.

#### Q : Est-il possible de spécifier la police ou la couleur du code en ligne dans Aspose.Words ?

 R : Oui, vous pouvez spécifier la police ou la couleur du code en ligne dans Aspose.Words. Vous pouvez utiliser le`Font.Name` et`Font.Color` propriétés du`Run` objet pour définir la police et la couleur du code en ligne. Par exemple, vous pouvez utiliser`run.Font.Name = "Courier New"` pour spécifier la police du code en ligne et`run.Font.Color = Color.Blue`pour préciser la couleur.

#### Q : Puis-je utiliser le code en ligne dans un paragraphe contenant d'autres éléments de texte ?

 R : Oui, vous pouvez utiliser le code en ligne dans un paragraphe contenant d'autres éléments de texte. Vous pouvez créer plusieurs`Run` objets pour représenter différentes parties du paragraphe, puis utilisez des balises de code en ligne pour formater uniquement les parties spécifiques en tant que code en ligne. Ensuite, vous pouvez les ajouter au paragraphe en utilisant le`Paragraph.AppendChild(run)` méthode.
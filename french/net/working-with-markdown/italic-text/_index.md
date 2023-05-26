---
title: Texte en italique
linktitle: Texte en italique
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à mettre du texte en italique avec le guide étape par étape Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/italic-text/
---

Dans cet exemple, nous vous expliquerons comment utiliser la fonctionnalité de texte en italique avec Aspose.Words pour .NET. Le texte en italique est utilisé pour souligner certaines parties d'un document.

## Étape 1 : Utiliser un générateur de documents

Tout d'abord, nous allons utiliser un générateur de document pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : Mettre le texte en italique

 Nous pouvons mettre le texte en italique en définissant la police`Italic` propriété à`true`.

```csharp
builder.Font.Italic = true;
builder.Writeln("This text will be in italics");
```

### Exemple de code source pour le texte en italique avec Aspose.Words pour .NET


```csharp
	// Utilisez un générateur de document pour ajouter du contenu au document.
	DocumentBuilder builder = new DocumentBuilder();

	// Mettez le texte en italique.
	builder.Font.Italic = true;
	builder.Writeln("This text will be Italic");
            
```

Félicitation ! Vous avez maintenant appris à utiliser la fonctionnalité de texte en italique avec Aspose.Words pour .NET.


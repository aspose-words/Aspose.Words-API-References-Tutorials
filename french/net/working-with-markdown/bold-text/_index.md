---
title: Texte en gras
linktitle: Texte en gras
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à mettre du texte en gras avec le guide étape par étape Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/bold-text/
---

Dans cet exemple, nous allons vous expliquer comment mettre du texte en gras avec Aspose.Words pour .NET. Le texte en gras le rend plus visible et lui donne plus d'importance.

## Étape 1 : Utiliser un générateur de documents

Tout d'abord, nous allons utiliser un générateur de document pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : texte en gras

 Nous pouvons mettre le texte en gras en définissant les paramètres du générateur de document`Font.Bold` propriété à`true`.

```csharp
builder.Font.Bold = true;
```

## Étape 3 : Ajouter du contenu au document

 Nous pouvons maintenant ajouter du contenu au document à l'aide des méthodes du générateur de documents, telles que`Writeln`, qui ajoute une ligne de texte.

```csharp
builder.Writeln("This text will be bold");
```

## Exemple de code source pour le texte en gras à l'aide de Aspose.Words pour .NET


```csharp
	// Utilisez un générateur de document pour ajouter du contenu au document.
	DocumentBuilder builder = new DocumentBuilder();

	// Mettez le texte en gras.
	builder.Font.Bold = true;
	builder.Writeln("This text will be Bold");  
```

Félicitation ! Vous avez maintenant appris à mettre du texte en gras avec Aspose.Words pour .NET.



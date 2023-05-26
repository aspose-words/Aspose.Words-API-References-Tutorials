---
title: Liste ordonnée
linktitle: Liste ordonnée
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à créer une liste ordonnée avec le guide étape par étape Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/ordered-list/
---

Dans cet exemple, nous expliquerons comment utiliser la fonctionnalité de liste ordonnée avec Aspose.Words pour .NET. La liste ordonnée vous permet d'organiser les éléments de manière séquentielle avec des numéros.

## Étape 1 : Utiliser un générateur de documents

Tout d'abord, nous allons utiliser un générateur de document pour créer un nouveau document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Application du format de liste ordonnée

Nous appliquerons le format de liste ordonnée en utilisant le générateur de document`ApplyBulletDefault` méthode. Nous pouvons également personnaliser le format de numérotation en accédant aux niveaux de liste et en définissant le format souhaité.

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## Étape 3 : Ajouter des éléments à la liste

 Nous pouvons ajouter des éléments à la liste en utilisant le générateur de documents`Writeln` méthode.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Étape 4 : Indentez la liste

 Nous pouvons indenter la liste en utilisant le générateur de documents`ListIndent` méthode.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## Étape 5 : Enregistrer le document

Enfin, nous pouvons enregistrer le document dans le format souhaité.

### Exemple de code source pour la liste ordonnée avec Aspose.Words pour .NET

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ListFormat.ApplyBulletDefault();
	builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
	builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

	builder.Writeln("Item 1");
	builder.Writeln("Item 2");

	builder.ListFormat.ListIndent();

	builder.Writeln("Item 2a");
	builder.Writeln("Item 2b");
            
```

Félicitation ! Vous avez maintenant appris à utiliser la fonctionnalité de liste ordonnée avec Aspose.Words pour .NET.


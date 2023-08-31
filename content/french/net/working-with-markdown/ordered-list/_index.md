---
title: Liste ordonnée
linktitle: Liste ordonnée
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment créer une liste ordonnée avec Aspose.Words pour .NET Guide étape par étape.
type: docs
weight: 10
url: /fr/net/working-with-markdown/ordered-list/
---

Dans cet exemple, nous expliquerons comment utiliser la fonctionnalité de liste ordonnée avec Aspose.Words pour .NET. La liste ordonnée vous permet d'organiser les éléments de manière séquentielle avec des numéros.

## Étape 1 : Utiliser un générateur de documents

Tout d’abord, nous utiliserons un générateur de documents pour créer un nouveau document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Application du format de liste ordonnée

 Nous appliquerons le format de liste ordonnée en utilisant le générateur de documents`ApplyBulletDefault`méthode. Nous pouvons également personnaliser le format de numérotation en accédant aux niveaux de liste et en définissant le format souhaité.

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## Étape 3 : Ajouter des éléments à la liste

 Nous pouvons ajouter des éléments à la liste en utilisant le générateur de documents`Writeln` méthode.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Étape 4 : mettre en retrait la liste

 Nous pouvons indenter la liste en utilisant le générateur de documents`ListIndent` méthode.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## Étape 5 : Sauvegarde du document

Enfin, nous pouvons enregistrer le document au format souhaité.

### Exemple de code source pour une liste ordonnée avec Aspose.Words pour .NET

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


### FAQ

#### Q : Comment créer une liste ordonnée dans Markdown ?

R : Pour créer une liste ordonnée dans Markdown, commencez chaque élément de la liste par un nombre suivi d'un point (`1.`, `2.`, `3.`), suivi d'un espace.

#### Q : Pouvons-nous imbriquer des listes ordonnées dans Markdown ?

R : Oui, il est possible d'imbriquer des listes ordonnées dans Markdown en ajoutant quatre espaces de décalage devant chaque élément de liste imbriqué.

#### Q : Comment personnaliser la numérotation des listes ordonnées ?

R : Dans Markdown standard, la numérotation des listes ordonnées est générée automatiquement. Cependant, certains éditeurs Markdown permettent de le personnaliser à l'aide d'extensions spécifiques.

#### Q : Les listes ordonnées dans Markdown prennent-elles en charge l'indentation ?

R : Oui, les listes ordonnées dans Markdown prennent en charge l'indentation. Vous pouvez ajouter un décalage vers la gauche à l'aide d'espaces ou de tabulations.

#### Q : Des liens ou du texte en ligne peuvent-ils être ajoutés aux éléments de la liste ?

R : Oui, vous pouvez ajouter des liens ou du texte en ligne pour répertorier les éléments en utilisant la syntaxe Markdown appropriée.
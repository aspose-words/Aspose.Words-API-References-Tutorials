---
title: Liste à puces
linktitle: Liste à puces
second_title: API de traitement de documents Aspose.Words
description: Apprenez à créer une liste à puces avec le guide étape par étape Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/bulleted-list/
---

Dans ce didacticiel, nous allons vous expliquer comment créer une liste à puces avec Aspose.Words pour .NET. Une liste à puces est utilisée pour répertorier les éléments sans utiliser de numérotation.

## Étape 1 : Utiliser un générateur de documents

Tout d'abord, nous allons utiliser un générateur de document pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : Application d'une liste à puces par défaut

 Nous pouvons appliquer une liste à puces par défaut à l'aide du générateur de documents`ApplyBulletDefault` méthode.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## Étape 3 : Personnaliser le format des puces

 Nous pouvons personnaliser le format des puces en accédant aux propriétés de`ListFormat.List.ListLevels[0]`. Dans cet exemple, nous utilisons le tiret "-" comme puce.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## Étape 4 : Ajouter des éléments à la liste

 Nous pouvons maintenant ajouter des éléments à la liste à puces à l'aide de l'outil de création de documents`Writeln` méthode.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Étape 5 : Suppression de l'indentation de la liste

 Si nous voulons créer une sous-liste, nous pouvons augmenter l'indentation en utilisant le`ListFormat.ListIndent()` méthode. Dans cet exemple, nous ajoutons une sous-liste aux éléments 2a et 2b.

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### Exemple de code source pour la liste à puces utilisant Aspose.Words pour .NET


```csharp
// Utilisez un générateur de document pour ajouter du contenu au document.
DocumentBuilder builder = new DocumentBuilder();

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

Félicitation ! Vous avez maintenant appris à créer une liste à puces avec Aspose.Words pour .NET.

### FAQ

#### Q : Comment créer une liste à puces dans Markdown ?

R : Pour créer une liste à puces dans Markdown, commencez chaque élément de la liste par un symbole de puce (`-`, `*` , ou`+`), suivi d'un espace.

#### Q : Pouvez-vous imbriquer des listes à puces dans Markdown ?

R : Oui, il est possible d'imbriquer des listes à puces dans Markdown en ajoutant quatre espaces décalés devant chaque élément de liste imbriqué.

#### Q : Comment personnaliser les puces ?

R : Dans le Markdown standard, les puces sont prédéfinies. Cependant, certains éditeurs Markdown vous permettent de les personnaliser à l'aide d'extensions spécifiques.

#### Q : Les listes à puces de Markdown prennent-elles en charge l'indentation ?

R : Oui, les listes à puces dans Markdown prennent en charge l'indentation. Vous pouvez ajouter un décalage vers la gauche en utilisant des espaces ou des tabulations.

#### Q : Des liens ou du texte en ligne peuvent-ils être ajoutés aux éléments de la liste ?

R : Oui, vous pouvez ajouter des liens ou du texte en ligne aux éléments de liste en utilisant la syntaxe Markdown appropriée.

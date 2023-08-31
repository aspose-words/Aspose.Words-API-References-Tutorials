---
title: La règle horizontale
linktitle: La règle horizontale
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer une règle horizontale avec le guide étape par étape d'Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/horizontal-rule/
---

Dans cet exemple, nous allons vous montrer comment utiliser la fonctionnalité de règle horizontale avec Aspose.Words pour .NET. Les règles horizontales sont utilisées pour séparer visuellement les sections d'un document.

## Étape 1 : Utiliser un générateur de documents

Tout d’abord, nous utiliserons un générateur de documents pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : Insérer une règle horizontale

 On peut insérer une règle horizontale en utilisant le`InsertHorizontalRule` méthode du générateur de documents.

```csharp
builder. InsertHorizontalRule();
```

## Exemple de code source pour une règle horizontale avec Aspose.Words for .NET

```csharp
// Utilisez un générateur de documents pour ajouter du contenu au document.
DocumentBuilder builder = new DocumentBuilder();

// Insérez une règle horizontale.
builder.InsertHorizontalRule();
```

Félicitation ! Vous avez maintenant appris à utiliser la fonctionnalité de règle horizontale avec Aspose.Words for .NET.


### FAQ

#### Q : Comment créer une règle horizontale dans Markdown ?

R : Pour créer une règle horizontale dans Markdown, vous pouvez utiliser l'un des symboles suivants sur une ligne vide : trois astérisques (\***), trois tirets (\---), ou trois traits de soulignement (\___).

#### Q : Puis-je personnaliser l’apparence d’une règle horizontale dans Markdown ?

R : Dans Markdown standard, il n'existe aucun moyen de personnaliser l'apparence des règles horizontales. Cependant, certains éditeurs et extensions Markdown avancés offrent des fonctionnalités de personnalisation supplémentaires.

#### Q : Les règles horizontales sont-elles prises en charge par tous les éditeurs Markdown ?

R : Oui, les éditeurs Markdown les plus populaires prennent en charge les règles horizontales. Cependant, il est toujours préférable de vérifier la documentation de votre fournisseur spécifique pour vous assurer qu'elle est prise en charge.

#### Q : Quels autres éléments puis-je créer dans Markdown ?

R : En plus des règles horizontales, vous pouvez créer des titres, des paragraphes, des listes, des liens, des images, des tableaux et bien plus encore dans Markdown.
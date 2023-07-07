---
title: La règle horizontale
linktitle: La règle horizontale
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à insérer une règle horizontale avec le guide pas à pas Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/horizontal-rule/
---

Dans cet exemple, nous allons vous montrer comment utiliser la fonction de règle horizontale avec Aspose.Words pour .NET. La règle horizontale est utilisée pour séparer visuellement les sections d'un document.

## Étape 1 : Utiliser un générateur de documents

Tout d'abord, nous allons utiliser un générateur de document pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : Insertion d'une règle horizontale

 Nous pouvons insérer une règle horizontale en utilisant le`InsertHorizontalRule` méthode du générateur de documents.

```csharp
builder. InsertHorizontalRule();
```

## Exemple de code source pour la règle horizontale avec Aspose.Words pour .NET

```csharp
// Utilisez un générateur de document pour ajouter du contenu au document.
DocumentBuilder builder = new DocumentBuilder();

// Insérez une règle horizontale.
builder.InsertHorizontalRule();
```

Félicitation ! Vous avez maintenant appris à utiliser la fonction de règle horizontale avec Aspose.Words pour .NET.


### FAQ

#### Q : Comment créer une règle horizontale dans Markdown ?

R : Pour créer une règle horizontale dans Markdown, vous pouvez utiliser l'un des symboles suivants sur une ligne vide : trois astérisques (\***), trois tirets (\---), ou trois traits de soulignement (\___).

#### Q : Puis-je personnaliser l'apparence d'une règle horizontale dans Markdown ?

R : Dans Markdown standard, il n'y a aucun moyen de personnaliser l'apparence des règles horizontales. Cependant, certains éditeurs et extensions Markdown avancés offrent des fonctionnalités de personnalisation supplémentaires.

#### Q : Les règles horizontales sont-elles prises en charge par tous les éditeurs Markdown ?

R : Oui, les éditeurs Markdown les plus populaires prennent en charge les règles horizontales. Cependant, il est toujours préférable de vérifier la documentation de votre fournisseur spécifique pour vous assurer qu'il est pris en charge.

#### Q : Quels autres éléments puis-je créer dans Markdown ?

R : En plus des règles horizontales, vous pouvez créer des titres, des paragraphes, des listes, des liens, des images, des tableaux, etc. dans Markdown.
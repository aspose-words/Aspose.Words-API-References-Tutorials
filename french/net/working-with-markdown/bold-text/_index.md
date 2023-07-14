---
title: Texte en gras
linktitle: Texte en gras
second_title: API de traitement de documents Aspose.Words
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


### FAQ

#### Q : Comment puis-je mettre du texte en gras dans Aspose.Words ?

 R : Pour mettre du texte en gras dans Aspose.Words, vous pouvez utiliser le`Font.Bold`propriété de la`Run`objet. Vous pouvez définir cette propriété sur`true` au texte spécifique en gras. Par exemple, vous pouvez utiliser`run.Font.Bold=true` pour mettre en gras le texte à l'intérieur du`Run` objet.

#### Q : Est-il possible de mettre en gras plusieurs éléments de texte dans le même paragraphe ?

 R : Oui, vous pouvez mettre en gras plusieurs éléments de texte dans un seul paragraphe en utilisant plusieurs`Run` objets. Vous pouvez créer plusieurs`Run` objets et définissez les`Font.Bold` propriété à`true` pour chaque objet pour mettre en gras les parties de texte souhaitées. Ensuite, vous pouvez les ajouter au paragraphe en utilisant le`Paragraph.AppendChild(run)` méthode.

#### Q : Puis-je mettre en gras du texte qui se trouve dans un tableau ou une cellule dans Aspose.Words ?

 R : Oui, vous pouvez mettre en gras le texte qui se trouve dans un tableau ou une cellule dans Aspose.Words. Vous pouvez accéder à la cellule ou au paragraphe de votre choix à l'aide des méthodes appropriées, puis appliquer la mise en forme en gras à l'aide de la`Font.Bold`propriété de la`Run` ou`Paragraph` objet.
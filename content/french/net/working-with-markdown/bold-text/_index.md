---
title: Texte en gras
linktitle: Texte en gras
second_title: API de traitement de documents Aspose.Words
description: Apprenez à mettre du texte en gras avec le guide étape par étape d'Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/bold-text/
---

Dans cet exemple, nous allons vous expliquer comment mettre du texte en gras avec Aspose.Words pour .NET. Le texte en gras le rend plus visible et lui donne plus de visibilité.

## Étape 1 : Utiliser un générateur de documents

Tout d’abord, nous utiliserons un générateur de documents pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : Texte en gras

 Nous pouvons mettre le texte en gras en définissant le paramètre du générateur de documents`Font.Bold`propriété à`true`.

```csharp
builder.Font.Bold = true;
```

## Étape 3 : ajouter du contenu au document

 Nous pouvons désormais ajouter du contenu au document à l'aide des méthodes de création de documents, telles que`Writeln`, ce qui ajoute une ligne de texte.

```csharp
builder.Writeln("This text will be bold");
```

## Exemple de code source pour du texte en gras utilisant Aspose.Words pour .NET


```csharp
// Utilisez un générateur de documents pour ajouter du contenu au document.
DocumentBuilder builder = new DocumentBuilder();

// Mettez le texte en gras.
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

Félicitation ! Vous avez maintenant appris à mettre du texte en gras avec Aspose.Words pour .NET.


### FAQ

#### Q : Comment puis-je mettre du texte en gras dans Aspose.Words ?

 R : Pour mettre le texte en gras dans Aspose.Words, vous pouvez utiliser l'option`Font.Bold` propriété du`Run`objet. Vous pouvez définir cette propriété sur`true` mettre en gras un texte spécifique. Par exemple, vous pouvez utiliser`run.Font.Bold=true` pour mettre le texte en gras à l'intérieur du`Run` objet.

#### Q : Est-il possible de mettre en gras plusieurs morceaux de texte dans un même paragraphe ?

 R : Oui, vous pouvez mettre en gras plusieurs morceaux de texte dans un seul paragraphe en utilisant plusieurs`Run` objets. Vous pouvez créer plusieurs`Run` objets et définir le`Font.Bold`propriété à`true` pour chaque objet, mettez en gras les parties souhaitées du texte. Ensuite, vous pouvez les ajouter au paragraphe en utilisant le`Paragraph.AppendChild(run)` méthode.

#### Q : Puis-je mettre en gras le texte d'un tableau ou d'une cellule dans Aspose.Words ?

 R : Oui, vous pouvez mettre en gras le texte d’un tableau ou d’une cellule dans Aspose.Words. Vous pouvez accéder à la cellule ou au paragraphe souhaité en utilisant les méthodes appropriées, puis appliquer la mise en forme en gras à l'aide de l'option`Font.Bold` propriété du`Run` ou`Paragraph` objet.
---
title: Déplacer vers la section
linktitle: Déplacer vers la section
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour utiliser Déplacer vers la section dans Aspose.Words pour .NET manipuler des sections et des paragraphes dans des documents Word.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/move-to-section/
---

Dans cet exemple, nous vous expliquerons comment utiliser la fonction Déplacer vers la section de Aspose.Words pour .NET étape par étape en utilisant le code source C# fourni. Cette fonctionnalité vous permet de naviguer et de manipuler différentes sections à l'intérieur d'un document Word. Suivez les étapes ci-dessous pour intégrer cette fonctionnalité dans votre application.

## Étape 1 : Créer un nouveau document et ajouter une section

Tout d'abord, nous devons créer un nouveau document et y ajouter une section. Utilisez le code suivant pour accomplir cette étape :

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));
```

Ce code crée un nouveau document vide et ajoute une section à ce document.

## Étape 2 : Déplacez le DocumentBuilder vers la deuxième section et ajoutez du texte

Ensuite, nous devons déplacer le DocumentBuilder vers la deuxième section du document et y ajouter du texte. Utilisez le code suivant pour effectuer cette étape :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");
```

Ce code crée un DocumentBuilder à partir du document existant, puis déplace le curseur du DocumentBuilder vers la deuxième section du document. Enfin, il ajoute le texte spécifié à cette section.

## Étape 3 : Charger un document avec des paragraphes existants

Si vous souhaitez travailler avec un document existant contenant des paragraphes, vous pouvez charger ce document à l'aide du code suivant :

```csharp
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);
```

Ce code charge le document spécifié (remplacez "MyDir + "Paragraphs.docx""avec le chemin d'accès réel à votre document) et accède à la collection de paragraphes de la première section du document. La ligne`Assert.AreEqual(22, paragraphs.Count);` vérifie que le document contient 22 paragraphes.

## Étape 4 : créer un DocumentBuilder pour un document

Vous pouvez créer le curseur DocumentBuilder sur un paragraphe spécifique à l'aide d'index positionnels.

```csharp
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));
```

## Étape 5 : Déplacez le curseur vers un paragraphe spécifique


Vous pouvez déplacer le curseur DocumentBuilder vers un paragraphe spécifique à l'aide d'index positionnels. Voici comment procéder :

```csharp
builder. MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph.");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

Ce code déplace le curseur du DocumentBuilder au troisième paragraphe de la deuxième section (paragraphe à l'index 2) et à la position 10. Ensuite, il ajoute un nouveau paragraphe avec du texte et vérifie que le curseur est bien positionné sur ce nouveau paragraphe.

### Exemple de code source pour Move To Move To Section en utilisant Aspose.Words pour .NET

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));

// Déplacez un DocumentBuilder vers la deuxième section et ajoutez du texte.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");

// Créer un document avec des paragraphes.
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);

//Lorsque nous créons un DocumentBuilder pour un document, son curseur est au tout début du document par défaut,
// et tout contenu ajouté par le DocumentBuilder sera simplement ajouté au document.
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

// Vous pouvez déplacer le curseur à n'importe quelle position dans un paragraphe.
builder.MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph. ");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

C'est tout ! Vous avez maintenant compris comment utiliser la fonctionnalité de déplacement vers la section d'Aspose.Words pour .NET à l'aide du code source fourni. Vous pouvez désormais intégrer cette fonctionnalité dans votre propre application et manipuler dynamiquement les sections et paragraphes de vos documents Word.


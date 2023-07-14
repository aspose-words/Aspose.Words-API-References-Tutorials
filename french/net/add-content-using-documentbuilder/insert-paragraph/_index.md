---
title: Insérer un paragraphe
linktitle: Insérer un paragraphe
second_title: API de traitement de documents Aspose.Words
description: Apprenez à insérer des paragraphes formatés dans des documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/insert-paragraph/
---

Dans ce didacticiel complet, vous apprendrez à insérer des paragraphes dans un document Word à l'aide de Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure d'ajouter des paragraphes formatés à vos documents.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : créer un nouveau document et DocumentBuilder
Pour commencer, créez un nouveau document à l'aide de la classe Document et initialisez un objet DocumentBuilder :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Définir la police et le formatage
Ensuite, configurez les propriétés de la police et la mise en forme des paragraphes à l'aide des objets Font et ParagraphFormat respectivement :

```csharp
Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;
```

## Étape 3 : Insérer un paragraphe
Après avoir configuré la police et le formatage, utilisez la méthode Writeln de la classe DocumentBuilder pour insérer un paragraphe entier :

```csharp
builder.Writeln("A whole paragraph.");
```

## Étape 4 : Enregistrer le document
Après avoir inséré le paragraphe, enregistrez le document dans un fichier à l'aide de la méthode Save de la classe Document :

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## Exemple de code source pour insérer un paragraphe en utilisant Aspose.Words pour .NET
Voici le code source complet pour insérer un paragraphe en utilisant Aspose.Words pour .NET :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;

builder.Writeln("A whole paragraph.");

doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment insérer des paragraphes formatés dans un document Word en utilisant Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais ajouter des paragraphes personnalisés avec des polices, une mise en forme et un alignement spécifiques à vos documents.
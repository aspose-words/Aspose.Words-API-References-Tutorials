---
title: Insérer un lien hypertexte
linktitle: Insérer un lien hypertexte
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à insérer des liens hypertexte dans des documents Word à l'aide du guide étape par étape Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/insert-hyperlink/
---

Dans ce didacticiel complet, vous apprendrez à insérer des liens hypertexte dans un document Word à l'aide d'Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure d'ajouter des hyperliens cliquables à vos documents.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : créer un nouveau document et DocumentBuilder
Pour commencer, créez un nouveau document à l'aide de la classe Document et initialisez un objet DocumentBuilder :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Insérer un lien hypertexte
Ensuite, utilisez la méthode Write de la classe DocumentBuilder pour ajouter du texte et formatez le lien hypertexte en définissant les propriétés de couleur et de soulignement :

```csharp
builder.Write("Please make sure to visit ");
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;

builder.InsertHyperlink("Aspose Website", "http://www.aspose.com", faux);

builder.Font.ClearFormatting();
builder.Write(" for more information.");
```

## Étape 3 : Enregistrer le document
Après avoir inséré le lien hypertexte, enregistrez le document dans un fichier à l'aide de la méthode Save de la classe Document :

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHyperlink.docx");
```

## Exemple de code source pour insérer un lien hypertexte à l'aide d'Aspose.Words pour .NET
Voici le code source complet pour insérer un lien hypertexte en utilisant Aspose.Words pour .NET :

Les liens hypertexte sont un moyen puissant d'améliorer l'interactivité et l'utilité de vos documents Word. Ils peuvent être utilisés pour référencer des ressources externes, fournir des informations supplémentaires ou créer des éléments de navigation dans le document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Please make sure to visit ");
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;

builder.InsertHyperlink("Aspose Website", "http://www.aspose.com", faux);

builder.Font.ClearFormatting();
builder.Write(" for more information.");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHyperlink.docx");
```

N'oubliez pas d'ajuster le code en fonction de vos besoins spécifiques, y compris le texte du lien hypertexte et l'URL. Améliorez-le avec une mise en forme ou des fonctionnalités supplémentaires selon vos besoins.

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment insérer des liens hypertexte dans un document Word en utilisant Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais ajouter des hyperliens cliquables à vos documents, dirigeant les lecteurs vers des sites Web externes ou des URL spécifiques.


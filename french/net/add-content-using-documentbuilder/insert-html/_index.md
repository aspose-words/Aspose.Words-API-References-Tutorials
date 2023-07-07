---
title: Insérer HTML
linktitle: Insérer HTML
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à insérer du contenu HTML dans des documents Word à l'aide d'Aspose.Words pour .NET. Guide étape par étape.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/insert-html/
---

Dans ce didacticiel complet, vous apprendrez à insérer du contenu HTML dans un document Word à l'aide de Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure d'ajouter des éléments HTML, une mise en forme et des styles à vos documents Word.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : créer un nouveau document et DocumentBuilder
Pour commencer, créez un nouveau document à l'aide de la classe Document et initialisez un objet DocumentBuilder :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Insérer du contenu HTML
Ensuite, utilisez la méthode InsertHtml de la classe DocumentBuilder pour insérer du contenu HTML dans le document. Vous pouvez inclure des balises HTML, des attributs et un style dans la chaîne HTML :

```csharp
builder.InsertHtml(
	"<P align='right'>Paragraph right</P>" +
	"<b>Implicit paragraph left</b>" +
	"<div align='center'>Div center</div>" +
	"<h1 align='left'>Heading 1 left.</h1>");
```

## Étape 3 : Enregistrer le document
Après avoir inséré le contenu HTML, enregistrez le document dans un fichier à l'aide de la méthode Save de la classe Document :

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHtml.docx");
```

## Exemple de code source pour insérer du HTML à l'aide d'Aspose.Words pour .NET
Voici le code source complet pour insérer du contenu HTML dans un document Word à l'aide d'Aspose.Words pour .NET :
Cette fonctionnalité est particulièrement utile lorsque vous avez du contenu HTML existant que vous souhaitez inclure dans vos documents Word tout en préservant la mise en forme et la mise en page d'origine.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertHtml(
	"<P align='right'>Paragraph right</P>" +
	"<b>Implicit paragraph left</b>" +
	"<div align='center'>Div center</div>" +
	"<h1 align='left'>Heading 1 left.</h1>");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHtml.docx");
```

N'oubliez pas d'ajuster le code en fonction de votre contenu HTML spécifique et de vos exigences. Assurez-vous que votre HTML est bien formé et compatible avec Aspose.Words pour .NET.

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment insérer du contenu HTML dans un document Word en utilisant Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais incorporer des éléments, des mises en forme et des styles HTML dans vos documents Word.



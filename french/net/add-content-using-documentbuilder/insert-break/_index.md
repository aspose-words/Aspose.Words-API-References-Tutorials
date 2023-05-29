---
title: Insérer un saut
linktitle: Insérer un saut
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à insérer des sauts de page dans des documents Word à l'aide d'Aspose.Words pour .NET. Guide étape par étape.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/insert-break/
---

Dans cet exemple complet, vous apprendrez à insérer des sauts de page dans un document Word à l'aide de la méthode InsertBreak dans Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure de contrôler les sauts de page dans votre document.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : créer un nouveau document et DocumentBuilder
Pour commencer, créez un nouveau document à l'aide de la classe Document et initialisez un objet DocumentBuilder :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Insérer du contenu et des sauts de page
Ensuite, utilisez la méthode Writeln de la classe DocumentBuilder pour ajouter du contenu au document. Pour insérer un saut de page, utilisez la méthode InsertBreak avec le paramètre BreakType.PageBreak :

```csharp
builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");
```

## Étape 3 : Enregistrer le document
Après avoir inséré le contenu et les sauts de page, enregistrez le document dans un fichier à l'aide de la méthode Save de la classe Document :

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

### Exemple de code source pour insérer un saut à l'aide d'Aspose.Words pour .NET
Voici le code source complet pour insérer des sauts de page en utilisant Aspose.Words pour .NET :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

N'oubliez pas d'ajuster le code en fonction de vos besoins spécifiques et de l'améliorer avec des fonctionnalités supplémentaires si nécessaire.


## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment insérer des sauts de page dans un document Word en utilisant Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais contrôler la pagination et la mise en page de votre document en insérant des sauts de page aux positions souhaitées.

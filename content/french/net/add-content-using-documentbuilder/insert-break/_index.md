---
title: Insérer un saut dans un document Word
linktitle: Insérer un saut dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer des sauts de page dans des documents Word à l'aide d'Aspose.Words pour .NET. Guide étape par étape.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/insert-break/
---
Dans cet exemple complet, vous apprendrez comment insérer des sauts de page dans un document Word à l'aide de la méthode InsertBreak dans Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure de contrôler les sauts de page dans votre document.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : Créer un nouveau document et DocumentBuilder
Pour commencer, créez un nouveau document à l'aide de la classe Document et initialisez un objet DocumentBuilder :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Insérer du contenu et des sauts de page
Ensuite, utilisez la méthode Writeln de la classe DocumentBuilder pour ajouter du contenu au document. Pour insérer un saut de page, utilisez la méthode InsertBreak avec le paramètre BreakType.PageBreak :

```csharp
builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");
```

## Étape 3 : Enregistrez le document
Après avoir inséré le contenu et les sauts de page, enregistrez le document dans un fichier à l'aide de la méthode Save de la classe Document :

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

### Exemple de code source pour insérer un saut à l'aide d'Aspose.Words pour .NET
Voici le code source complet pour insérer des sauts de page à l’aide d’Aspose.Words for .NET :

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
Toutes nos félicitations! Vous avez appris avec succès comment insérer des sauts de page dans un document Word à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais contrôler la pagination et la mise en page de votre document en insérant des sauts de page aux positions souhaitées.

### FAQ

#### Q : Puis-je insérer différents types de sauts en plus des sauts de page ?

R : Absolument ! Aspose.Words for .NET prend en charge différents types de sauts, notamment les sauts de page, les sauts de colonne et les sauts de section. Vous pouvez utiliser la méthode InsertBreak avec différents paramètres BreakType pour insérer le type de pause souhaité.

#### Q : Puis-je insérer des sauts de page dans des sections spécifiques du document ?

: Oui, vous pouvez insérer des sauts de page à des endroits spécifiques du document. En utilisant DocumentBuilder, vous pouvez contrôler l'emplacement des sauts de page en fonction du contenu et de la structure de votre document.

#### Q : Les sauts de page seront-ils conservés lors de l'enregistrement du document dans différents formats de fichier ?

R : Oui, les sauts de page insérés à l'aide d'Aspose.Words pour .NET sont conservés lors de l'enregistrement du document dans différents formats de fichier, tels que DOCX, PDF ou RTF. Cela garantit une pagination et une mise en page cohérentes dans différents formats de fichiers.

#### Q : Puis-je personnaliser l’apparence des sauts de page ?

R : Les sauts de page ne sont pas visibles dans le document lui-même, mais vous pouvez ajuster le formatage et la mise en page du contenu avant et après les sauts de page pour contrôler l'apparence du document.

#### Q : Aspose.Words for .NET convient-il aux applications de bureau et Web ?

R : Oui, Aspose.Words for .NET est une bibliothèque polyvalente adaptée aux applications de bureau et Web. Que vous créiez une application Windows ou un système Web, vous pouvez intégrer la bibliothèque sans effort.
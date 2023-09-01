---
title: Ajouter des marques Bidi dans un document Word
linktitle: Ajouter des marques Bidi dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Apprenez à ajouter des marques Bidi à un document Word à l'aide d'Aspose.Words for .NET et à créer des documents multilingues professionnels.
type: docs
weight: 10
url: /fr/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words for .NET est une bibliothèque puissante permettant de créer, modifier et manipuler des documents Word dans une application C#. Parmi les fonctionnalités offertes par Aspose.Words figure la possibilité d'ajouter des marques Bidi (bidirectionnelles) à un document. Dans ce guide, nous vous expliquerons comment utiliser le code source C# d'Aspose.Words for .NET pour ajouter des marques Bidi à un document.

## Comprendre la bibliothèque Aspose.Words

Avant de plonger dans le code, il est important de comprendre la bibliothèque Aspose.Words pour .NET. Aspose.Words est une bibliothèque populaire qui rend le traitement de mots avec des documents Word facile et efficace. Il offre un large éventail de fonctionnalités pour créer, éditer et manipuler des documents Word, notamment l'ajout de marques Bidi.

## Création du document et ajout de contenu

La première étape consiste à créer un nouveau document et à y ajouter du contenu. Utilisez la classe Document pour créer une nouvelle instance de document. Utilisez ensuite la classe DocumentBuilder pour ajouter du texte au document. Voici un exemple :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

Dans cet exemple, nous créons un nouveau document et utilisons DocumentBuilder pour ajouter du texte. Nous avons ajouté trois lignes de texte : une en anglais, une en hébreu et une en arabe pour démontrer l'ajout de contenu dans différentes langues.

## Marques Bidi ajoutées

Une fois le contenu ajouté, nous pouvons désormais ajouter des marques Bidi au document. Pour cela, nous utilisons la classe TxtSaveOptions et nous définissons la propriété AddBidiMarks sur true. Voici comment:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

Dans cet exemple, nous créons une instance de TxtSaveOptions et définissons la propriété AddBidiMarks sur true. Ensuite, nous utilisons la méthode Save de la classe Document pour enregistrer le document avec les marques Bidi.

### Exemple de code source pour la fonctionnalité « Ajouter des marques Bidi » avec Aspose.Words pour .NET

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créer le document et ajouter du contenu
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

// Ajouter des marques Bidi
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## Conclusion

Dans ce guide, nous avons expliqué comment utiliser Aspose.Words pour .NET pour ajouter des marques Bidi à un document Word à l'aide du code source C# fourni. En suivant les étapes fournies, vous pouvez facilement ajouter des marques Bidi à vos documents Word dans votre application C#. Aspose.Words offre une flexibilité et une puissance considérables pour le traitement de texte avec le formatage du texte et la gestion des langues, vous permettant de créer des documents multilingues de manière professionnelle.

### Questions fréquemment posées

#### Q : Qu'est-ce qu'Aspose.Words pour .NET ?
Aspose.Words for .NET est une puissante bibliothèque permettant de créer, modifier et manipuler des documents Word dans une application C#. Il offre de nombreuses fonctionnalités pour le traitement de mots avec des documents Word, notamment l'ajout de marques Bidi (bidirectionnelles).

#### Q : Quelles fonctionnalités propose Aspose.Words pour .NET ?
Aspose.Words for .NET offre un large éventail de fonctionnalités pour créer, modifier et manipuler des documents Word. Certaines de ces fonctionnalités incluent la création de documents, l'ajout de contenu, le formatage du texte, la gestion de tableaux, la fusion et le fractionnement de documents, la conversion de documents, etc.

#### Q : Comment puis-je ajouter des marques Bidi à un document Word à l'aide d'Aspose.Words pour .NET ?
Vous pouvez ajouter des marques Bidi à un document Word en suivant ces étapes :

 Créez un nouveau document à l'aide du`Document` classe.

 Utilisez le`DocumentBuilder` classe pour ajouter du contenu au document.

 Une fois que vous avez ajouté le contenu, utilisez le`TxtSaveOptions` classe et définir le`AddBidiMarks` propriété à`true`.

 Enregistrez le document avec les marques Bidi en utilisant le`Save` méthode du`Document` classe.

#### Q : Aspose.Words prend-il en charge plusieurs langues pour ajouter des marques Bidi ?
Oui, Aspose.Words prend en charge plusieurs langues pour ajouter des marques Bidi. Vous pouvez ajouter des marques Bidi au texte dans différentes langues, telles que l'anglais, l'hébreu et l'arabe, à l'aide d'Aspose.Words pour .NET.

#### Q : Existe-t-il des options supplémentaires pour enregistrer le document avec les marques Bidi ?
 Oui, vous pouvez spécifier d'autres options lors de l'enregistrement du document avec des marques Bidi à l'aide de l'option`TxtSaveOptions` classe. Par exemple, vous pouvez définir le format d'enregistrement du document, les options d'encodage, etc.
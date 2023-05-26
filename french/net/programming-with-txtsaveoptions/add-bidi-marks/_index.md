---
title: Ajouter des marques bidis
linktitle: Ajouter des marques bidis
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à ajouter des marques Bidi à un document Word à l'aide d'Aspose.Words pour .NET et créez des documents multilingues professionnels.
type: docs
weight: 10
url: /fr/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words pour .NET est une bibliothèque puissante pour créer, éditer et manipuler des documents Word dans une application C#. Parmi les fonctionnalités offertes par Aspose.Words figure la possibilité d'ajouter des marques Bidi (bidirectionnelles) à un document. Dans ce guide, nous vous expliquerons comment utiliser le code source C # de Aspose.Words pour .NET pour ajouter des marques Bidi à un document.

## Comprendre la bibliothèque Aspose.Words

Avant de plonger dans le code, il est important de comprendre la bibliothèque Aspose.Words pour .NET. Aspose.Words est une bibliothèque populaire qui rend le travail avec les documents Word simple et efficace. Il offre un large éventail de fonctionnalités pour créer, éditer et manipuler des documents Word, y compris l'ajout de marques Bidi.

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

Dans cet exemple, nous créons un nouveau document et utilisons le DocumentBuilder pour ajouter du texte. Nous avons ajouté trois lignes de texte : une en anglais, une en hébreu et une en arabe pour illustrer l'ajout de contenu dans différentes langues.

## Marques Bidi ajoutées

Une fois le contenu ajouté, nous pouvons maintenant ajouter des marques Bidi au document. Pour cela, nous utilisons la classe TxtSaveOptions et nous définissons la propriété AddBidiMarks sur true. Voici comment:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

Dans cet exemple, nous créons une instance de TxtSaveOptions et définissons la propriété AddBidiMarks sur true. Ensuite, nous utilisons la méthode Save de la classe Document pour enregistrer le document avec les marques Bidi.

### Exemple de code source pour la fonctionnalité "Ajouter des marques Bidi" avec Aspose.Words pour .NET

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

Dans ce guide, nous avons expliqué comment utiliser Aspose.Words pour .NET pour ajouter des marques Bidi à un document Word à l'aide du code source C# fourni. En suivant les étapes fournies, vous pouvez facilement ajouter des marques Bidi à vos documents Word dans votre application C#. Aspose.Words offre une flexibilité et une puissance considérables pour travailler avec le formatage du texte et la gestion des langues, vous permettant de créer des documents multilingues de manière professionnelle.
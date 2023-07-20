---
title: Formatage de liste à plusieurs niveaux dans un document Word
linktitle: Formatage de liste à plusieurs niveaux dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Apprenez à créer une liste à plusieurs niveaux et à appliquer une mise en forme personnalisée dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/document-formatting/multilevel-list-formatting/
---
Dans ce didacticiel, nous allons vous montrer comment utiliser la mise en forme de liste à plusieurs niveaux dans la fonctionnalité de document Word avec Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et appliquer les modifications.

## Étape 1 : Création et configuration du document

Pour commencer, créez un nouveau document et un objet DocumentBuilder associé. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Formater la liste à plusieurs niveaux

Nous allons maintenant appliquer la mise en forme de la liste multiniveau en utilisant les méthodes disponibles dans l'objet DocumentBuilder. Voici comment:

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## Étape 3 : Enregistrer le document

 Après avoir inséré le champ du formulaire de saisie de texte, enregistrez le document à l'emplacement souhaité à l'aide de la`Save` méthode. Assurez-vous de fournir le chemin d'accès au fichier approprié :

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### Exemple de code source pour le formatage de liste à plusieurs niveaux à l'aide d'Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité de formatage de liste à plusieurs niveaux avec Aspose.Words pour .NET :


```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.1");
builder.Writeln("Item 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.2.1");
builder.Writeln("Item 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 3");

builder.ListFormat.RemoveNumbers();

doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

Avec ce code, vous pourrez créer une liste à plusieurs niveaux et appliquer le formatage approprié à chaque niveau en utilisant Aspose.Words pour .NET.


## Conclusion

Dans ce didacticiel, nous avons exploré le processus d'utilisation de la fonctionnalité de formatage de liste à plusieurs niveaux dans un document Word avec Aspose.Words pour .NET. En suivant les étapes décrites, vous pouvez créer des listes bien organisées à plusieurs niveaux, améliorant ainsi la structure et la lisibilité de vos documents.

### FAQ

#### Q : Qu'est-ce qu'une liste à plusieurs niveaux dans un document Word ?

R : Une liste à plusieurs niveaux dans un document Word est une liste hiérarchique qui vous permet d'organiser les éléments en différents niveaux de sous-éléments. Il aide à présenter les informations de manière structurée, ce qui facilite la compréhension du contenu par les lecteurs.

#### Q : Puis-je personnaliser l'apparence de la liste à plusieurs niveaux ?

: Oui, vous pouvez personnaliser l'apparence de la liste à plusieurs niveaux dans votre document Word. En appliquant différents styles, tels que des puces, des chiffres ou des lettres, et en ajustant l'indentation et l'espacement, vous pouvez créer une liste visuellement attrayante et organisée.

#### Q : Aspose.Words pour .NET prend-il en charge d'autres options de formatage de liste ?

R : Oui, Aspose.Words pour .NET fournit un ensemble complet de fonctionnalités pour le formatage des listes. Il prend en charge divers types de listes, notamment les listes à puces, les listes numérotées et les listes à plusieurs niveaux. Vous pouvez manipuler la mise en forme des listes, ajouter ou supprimer des éléments et personnaliser leur apparence.

#### Q : Puis-je utiliser Aspose.Words pour .NET pour travailler avec d'autres éléments de document ?

R : Oui, Aspose.Words pour .NET offre des fonctionnalités étendues pour travailler avec divers éléments de document, tels que des paragraphes, des tableaux, des images, etc. Il vous permet de créer, de modifier et de convertir des documents Word par programme, en rationalisant les tâches de traitement des documents.
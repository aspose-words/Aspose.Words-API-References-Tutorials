---
title: Insérer un objet Ole dans un document Word sous forme d'icône
linktitle: Insérer un objet Ole dans un document Word sous forme d'icône
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer un objet OLE dans un document Word sous forme d'icône avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

Voici un guide étape par étape pour expliquer le code source C# ci-dessous qui illustre comment insérer un objet OLE dans un document Word sous forme d'icône à l'aide d'Aspose.Words pour .NET.

## Étape 1 : Importez les références nécessaires
Avant de commencer, assurez-vous d'avoir importé les références nécessaires pour utiliser Aspose.Words for .NET dans votre projet. Cela inclut l'importation de la bibliothèque Aspose.Words et l'ajout des espaces de noms requis à votre fichier source.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Étape 2 : Créer un nouveau document et un générateur de documents
 Dans cette étape, nous allons créer un nouveau document en utilisant le`Document` classe et un générateur de documents utilisant le`DocumentBuilder` classe.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Insérer un objet OLE sous forme d'icône
 Utilisez le générateur de documents`InsertOleObjectAsIcon`méthode pour insérer un objet OLE sous forme d’icône dans le document. Spécifiez le chemin du fichier OLE, l'indicateur d'affichage, le chemin de l'icône et le nom de l'objet incorporé.

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## Étape 4 : Enregistrez le document
 Utilisez le document`Save` méthode pour enregistrer le document dans un fichier.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### Exemple de code source pour insérer un objet OLE sous forme d'icône avec Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

Il s'agit d'un exemple de code complet pour insérer un objet OLE sous forme d'icône avec Aspose.Words pour .NET. Assurez-vous d'importer les références nécessaires et suivez les étapes décrites précédemment pour intégrer ce code dans votre projet.

## Conclusion

En conclusion, nous avons exploré un guide étape par étape pour insérer un objet OLE sous forme d'icône dans un document Word à l'aide d'Aspose.Words pour .NET.

En suivant ces étapes, vous pourrez insérer avec succès un objet OLE sous forme d'icône dans vos documents Word à l'aide d'Aspose.Words pour .NET. Assurez-vous d'importer les références nécessaires et suivez attentivement les instructions pour obtenir les résultats souhaités.

### FAQ pour insérer un objet ole dans un document Word sous forme d'icône

#### Q. Quelles références sont nécessaires pour insérer un objet OLE en tant qu'icône dans un document Word à l'aide d'Aspose.Words pour .NET ?

R : Vous devez importer les références suivantes dans votre projet pour utiliser Aspose.Words for .NET :

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### Q. Comment créer un nouveau document et un générateur de documents dans Aspose.Words pour .NET ?

 R : Vous pouvez créer un nouveau document à l'aide du`Document` classe et un générateur de documents utilisant le`DocumentBuilder` classe. Voici un exemple :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q. Comment insérer un objet OLE comme icône dans le document ?

 R : Utilisez le générateur de documents`InsertOleObjectAsIcon` méthode pour insérer un objet OLE sous forme d’icône. Spécifiez le chemin du fichier OLE, l'indicateur d'affichage, le chemin de l'icône et le nom de l'objet incorporé. Voici un exemple :

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### Q. Comment enregistrer le document avec l'objet OLE inséré sous forme d'icône ?

 R : Utiliser le document`Save` méthode pour enregistrer le document dans un fichier. Voici un exemple :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```
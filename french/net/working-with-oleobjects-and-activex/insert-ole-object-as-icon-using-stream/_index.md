---
title: Insérer un objet Ole en tant qu'icône à l'aide de Stream
linktitle: Insérer un objet Ole en tant qu'icône à l'aide de Stream
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à insérer un objet OLE en tant qu'icône à l'aide d'un flux avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

Voici un guide étape par étape pour expliquer le code source C # ci-dessous qui illustre comment insérer un objet OLE sous forme d'icône à l'aide d'un flux avec Aspose.Words pour .NET.

## Étape 1 : Importez les références nécessaires
Avant de commencer, assurez-vous d'avoir importé les références nécessaires pour utiliser Aspose.Words pour .NET dans votre projet. Cela inclut l'importation de la bibliothèque Aspose.Words et l'ajout des espaces de noms requis à votre fichier source.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## Étape 2 : Créer un nouveau document et un générateur de documents
 Dans cette étape, nous allons créer un nouveau document en utilisant le`Document` classe et un générateur de documents utilisant la`DocumentBuilder` classe.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Insérer un objet OLE en tant qu'icône à partir d'un flux
 Utilisez le générateur de documents`InsertOleObjectAsIcon` méthode pour insérer un objet OLE sous forme d'icône à partir d'un flux dans le document. Spécifiez le flux de données, le type d'objet, le chemin de l'icône et le nom de l'objet intégré.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## Étape 4 : Enregistrez le document
 Utilisez le document`Save` méthode pour enregistrer le document dans un fichier.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### Exemple de code source pour insérer un objet OLE en tant qu'icône à l'aide d'un flux avec Aspose.Words pour .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

Il s'agit d'un exemple de code complet pour insérer un objet OLE en tant qu'icône à l'aide d'un flux avec Aspose.Words pour .NET. Assurez-vous d'importer les références nécessaires et suivez les étapes décrites précédemment pour intégrer ce code dans votre projet.

## Conclusion

Le guide étape par étape ci-dessus explique comment insérer un objet OLE en tant qu'icône dans un document Word à l'aide d'un flux avec Aspose.Words pour .NET. En suivant les étapes décrites, vous pourrez intégrer cette fonctionnalité dans votre projet. Assurez-vous d'importer les références nécessaires, créez un nouveau document et générateur de document, insérez l'objet OLE en tant qu'icône du flux, puis enregistrez le document. Utilisez l'exemple de code fourni comme point de départ et personnalisez-le selon vos besoins.

### FAQ

#### Q. Comment importer les références nécessaires pour utiliser Aspose.Words pour .NET ?

A. Pour importer les références nécessaires, vous devez suivre ces étapes :

 Ajoutez ce qui suit`using` instructions en haut de votre fichier source :

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
Assurez-vous d'avoir ajouté la bibliothèque Aspose.Words à votre projet.

#### Q. Comment créer un nouveau document et générateur de document en utilisant Aspose.Words pour .NET ?

A. Pour créer un nouveau document et générateur de document, vous pouvez suivre ces étapes :

 Utilisez le`Document` classe pour créer un nouveau document :

```csharp
Document doc = new Document();
```
 Utilisez le`DocumentBuilder` class pour créer un document builder associé au document créé précédemment :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q. Comment insérer un objet OLE en tant qu'icône à partir d'un flux à l'aide d'Aspose.Words pour .NET ?

A. Pour insérer un objet OLE sous forme d'icône à partir d'un flux, vous pouvez suivre ces étapes :

 Utilisez le`InsertOleObjectAsIcon` méthode du générateur de document pour insérer l'objet OLE :

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### Q. Comment enregistrer le document dans un fichier ?

A.  Pour enregistrer le document dans un fichier, vous pouvez utiliser le`Save` méthode du document spécifiant le chemin de destination :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### Q. Comment puis-je incorporer le code pour insérer un objet OLE sous la forme d'une icône à partir d'un flux dans mon projet ?

A. Pour intégrer le code d'insertion d'un objet OLE en tant qu'icône à partir d'un flux dans votre projet, procédez comme suit :
- Importez les références nécessaires en ajoutant les`using` déclarations.
-  Créez un nouveau document et un générateur de document à l'aide de`Document` et`DocumentBuilder` Des classes.
- Utilisez le code pour insérer l'objet OLE en tant qu'icône à partir d'un flux.
-  Enregistrez le document à l'aide de la`Save` méthode avec le chemin de destination approprié.

En suivant ces étapes, vous pourrez insérer avec succès un objet OLE en tant qu'icône à partir d'un flux à l'aide de Aspose.Words pour .NET. Assurez-vous de suivre les instructions et d'importer les références nécessaires pour obtenir les résultats souhaités.
---
title: Insérer un objet Ole dans Word avec le package Ole
linktitle: Insérer un objet Ole dans Word avec le package Ole
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer un objet OLE avec un package OLE dans un document à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

Voici un guide étape par étape pour expliquer le code source C# ci-dessous qui illustre comment insérer un objet OLE dans Word avec un package OLE à l'aide d'Aspose.Words pour .NET.

## Étape 1 : Importez les références nécessaires
Avant de commencer, assurez-vous d'avoir importé les références nécessaires pour utiliser Aspose.Words for .NET dans votre projet. Cela inclut l'importation de la bibliothèque Aspose.Words et l'ajout des espaces de noms requis à votre fichier source.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## Étape 2 : Créer un nouveau document et un générateur de documents
 Dans cette étape, nous allons créer un nouveau document en utilisant le`Document` classe et un générateur de documents utilisant le`DocumentBuilder` classe.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Insérer un objet OLE avec un package OLE
 Utilisez le générateur de documents`InsertOleObject`méthode pour insérer un objet OLE avec un package OLE dans le document. Spécifiez le flux de données, le type d'objet, les options d'affichage et d'autres paramètres nécessaires.

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}
```

## Étape 4 : Enregistrez le document
 Utilisez le document`Save` méthode pour enregistrer le document dans un fichier.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### Exemple de code source pour insérer un objet OLE avec un package OLE avec Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Il s'agit d'un exemple de code complet pour insérer un objet OLE avec un package OLE avec Aspose.Words pour .NET. Assurez-vous d'importer les références nécessaires et suivez les étapes décrites précédemment pour intégrer ce code dans votre projet.

## Conclusion

En conclusion, nous avons parcouru un guide étape par étape pour insérer un objet OLE dans un document Word avec un package OLE utilisant Aspose.Words pour .NET.

En suivant ces étapes, vous pourrez insérer avec succès des objets OLE avec des packages OLE dans vos documents Word à l'aide d'Aspose.Words pour .NET. Assurez-vous d'importer les références nécessaires et suivez attentivement les instructions pour obtenir les résultats souhaités.

### FAQ pour insérer un objet ole dans Word avec le package ole

#### Q : Quelles informations d'identification dois-je importer pour utiliser Aspose.Words for .NET ?

R : Pour utiliser Aspose.Words pour .NET, vous devez importer les références suivantes :

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### Q : Comment créer un nouveau document et un générateur de documents ?

 R : Vous pouvez créer un nouveau document à l'aide du`Document` classe et un générateur de documents utilisant le`DocumentBuilder` classe, comme indiqué ci-dessous :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### : Comment insérer un objet OLE avec un package OLE dans le document ?

 R : Utilisez le`InsertOleObject` méthode du générateur de documents (`DocumentBuilder`) pour insérer un objet OLE avec un package OLE dans le document. Spécifiez le flux de données, le type d'objet, les options d'affichage et d'autres paramètres nécessaires. Voici un exemple :

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}
```

#### Q : Comment enregistrer le document ?

 R : Utiliser le document`Save`méthode pour enregistrer le document dans un fichier. Voici un exemple :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### Q : Pouvez-vous fournir un exemple complet d'insertion d'un objet OLE avec un package OLE avec Aspose.Words pour .NET ?

R : Voici un exemple de code complet pour insérer un objet OLE avec un package OLE à l'aide d'Aspose.Words pour .NET. Assurez-vous d'importer les références nécessaires et suivez les étapes décrites précédemment pour intégrer ce code dans votre projet :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Ceci conclut notre didacticiel sur l'insertion d'un objet OLE avec un package OLE dans un document Word à l'aide d'Aspose.Words pour .NET. N'hésitez pas à importer les références nécessaires et suivez les étapes décrites pour intégrer ce code dans votre projet. Si vous avez d'autres questions, n'hésitez pas à nous contacter.
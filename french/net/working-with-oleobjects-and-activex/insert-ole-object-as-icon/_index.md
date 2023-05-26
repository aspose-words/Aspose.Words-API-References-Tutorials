---
title: Insérer un objet Ole en tant qu'icône
linktitle: Insérer un objet Ole en tant qu'icône
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à insérer un objet OLE sous forme d'icône avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

Voici un guide étape par étape pour expliquer le code source C # ci-dessous qui illustre comment insérer un objet OLE sous forme d'icône à l'aide de Aspose.Words pour .NET.

## Étape 1 : Importez les références nécessaires
Avant de commencer, assurez-vous d'avoir importé les références nécessaires pour utiliser Aspose.Words pour .NET dans votre projet. Cela inclut l'importation de la bibliothèque Aspose.Words et l'ajout des espaces de noms requis à votre fichier source.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Étape 2 : Créer un nouveau document et un générateur de documents
 Dans cette étape, nous allons créer un nouveau document en utilisant le`Document` classe et un générateur de documents utilisant la`DocumentBuilder` classe.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Insérer un objet OLE en tant qu'icône
 Utilisez le générateur de documents`InsertOleObjectAsIcon` méthode pour insérer un objet OLE sous forme d'icône dans le document. Spécifiez le chemin du fichier OLE, l'indicateur d'affichage, le chemin de l'icône et le nom de l'objet incorporé.

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## Étape 4 : Enregistrez le document
 Utilisez le document`Save` méthode pour enregistrer le document dans un fichier.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### Exemple de code source pour insérer un objet OLE en tant qu'icône avec Aspose.Words pour .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

Il s'agit d'un exemple de code complet pour insérer un objet OLE en tant qu'icône avec Aspose.Words pour .NET. Assurez-vous d'importer les références nécessaires et suivez les étapes décrites précédemment pour intégrer ce code dans votre projet.

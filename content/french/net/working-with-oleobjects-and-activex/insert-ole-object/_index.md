---
title: Insérer un objet Ole dans un document Word
linktitle: Insérer un objet Ole dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer un objet OLE dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-oleobjects-and-activex/insert-ole-object/
---

Voici un guide étape par étape pour expliquer le code source C# ci-dessous qui illustre comment insérer un objet OLE dans un document Word à l'aide d'Aspose.Words pour .NET.

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

## Étape 3 : Insérer un objet OLE
 Utilisez le générateur de documents`InsertOleObject` méthode pour insérer un objet OLE dans le document. Spécifiez l'URL de l'objet OLE, le type d'objet, les options d'affichage et d'autres paramètres nécessaires.

```csharp
builder. InsertOleObject("http://www.aspose.com", "fichierhtml", vrai, vrai, nul);
```

## Étape 4 : Enregistrez le document
 Utilisez le document`Save` méthode pour enregistrer le document dans un fichier.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### Exemple de code source pour insérer un objet OLE avec Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "fichierhtml", vrai, vrai, nul);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

Il s'agit d'un exemple de code complet pour insérer un objet OLE avec Aspose.Words pour .NET. Assurez-vous d'importer les références nécessaires et suivez les étapes décrites précédemment pour intégrer ce code dans votre projet.

## Conclusion

En conclusion, l'insertion d'objets OLE dans un document Word est une fonctionnalité puissante proposée par Aspose.Words for .NET. Grâce à cette bibliothèque, vous pouvez facilement intégrer des objets OLE tels que des fichiers HTML, des feuilles de calcul Excel, des présentations PowerPoint, etc., dans vos documents Word.

Dans cet article, nous avons parcouru un guide étape par étape pour expliquer le code source en C# qui illustre comment insérer un objet OLE dans un document Word. Nous avons couvert les références nécessaires, la création d'un nouveau document et d'un générateur de document, ainsi que les étapes pour insérer un objet OLE et enregistrer le document.

### FAQ pour insérer un objet OLE dans un document Word

#### Q : Quelles informations d'identification dois-je importer pour utiliser Aspose.Words for .NET ?

R : Pour utiliser Aspose.Words pour .NET, vous devez importer les références suivantes :

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### Q : Comment créer un nouveau document et un générateur de documents ?

 R : Vous pouvez créer un nouveau document à l'aide du`Document` classe et un générateur de documents utilisant le`DocumentBuilder` classe, comme indiqué ci-dessous :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q : Comment insérer un objet OLE dans le document ?

 R : Utilisez le`InsertOleObject`méthode du générateur de documents (`DocumentBuilder`) pour insérer un objet OLE dans le document. Spécifiez l'URL de l'objet OLE, le type d'objet, les options d'affichage et d'autres paramètres nécessaires. Voici un exemple :

```csharp
builder. InsertOleObject("http://www.aspose.com", "fichierhtml", vrai, vrai, nul);
```

#### Q : Comment enregistrer le document ?

 R : Utiliser le document`Save` méthode pour enregistrer le document dans un fichier. Voici un exemple :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### Q : Pouvez-vous fournir un exemple complet d’insertion d’un objet OLE avec Aspose.Words pour .NET ?

R : Voici un exemple de code complet pour insérer un objet OLE avec Aspose.Words pour .NET. Assurez-vous d'importer les références nécessaires et suivez les étapes décrites précédemment pour intégrer ce code dans votre projet :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "fichierhtml", vrai, vrai, nul);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

---
title: Cloner un document
linktitle: Cloner un document
second_title: API de traitement de documents Aspose.Words
description: Apprenez à cloner un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/clone-and-combine-documents/cloning-document/
---

Dans ce didacticiel, nous allons vous expliquer comment cloner un document Word à l'aide de la fonctionnalité de clonage d'Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et créer une copie exacte d'un document existant.

## Étape 1 : Chargement du document

Pour commencer, spécifiez votre répertoire de documents et chargez le document existant dans un objet Document. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## Étape 2 : Cloner le document

Nous allons maintenant cloner le document en créant une copie exacte de celui-ci. Voici comment:

```csharp
Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.ClonageDocument.docx");
```

### Exemple de code source pour le clonage de document à l'aide d'Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité de clonage de document Aspose.Words pour .NET :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";            
Document doc = new Document(MyDir + "Document.docx");

Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.CloningDocument.docx");
```

Avec ce code, vous pourrez cloner un document Word en utilisant Aspose.Words pour .NET. La copie exacte du document sera enregistrée sous un nouveau nom de fichier.


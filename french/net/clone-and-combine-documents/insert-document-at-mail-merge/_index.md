---
title: Insérer le document lors du publipostage
linktitle: Insérer le document lors du publipostage
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à insérer un document dans un autre pendant le publipostage à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/clone-and-combine-documents/insert-document-at-mail-merge/
---

Dans ce didacticiel, nous allons vous expliquer comment insérer un document dans un autre document lors du publipostage à l'aide de la fonctionnalité Insérer un document lors du publipostage d'Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et effectuer l'insertion du document.

## Étape 1 : Chargement du document principal

Pour commencer, spécifiez le répertoire de vos documents et chargez le document principal dans un objet Document. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Étape 2 : Configurer le publipostage

Configurons maintenant le publipostage et spécifions le rappel de fusion de champ pour insérer un document dans un autre document. Voici comment:

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Étape 3 : Exécution du publipostage

Nous exécuterons le publipostage en fournissant les noms des champs de fusion et les données correspondantes. Voici comment:

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

### Exemple de code source pour Insérer un document lors du publipostage à l'aide de Aspose.Words pour .NET

Voici le code source complet de la fonction Insérer un document dans le publipostage d'Aspose.Words pour .NET :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
// Le document principal contient un champ de fusion appelé "Document_1".
// Les données correspondantes pour ce champ contiennent un chemin complet vers le document.
// Cela devrait être inséré dans ce champ.
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

Avec ce code, vous pourrez insérer un document dans un autre document lors du publipostage en utilisant Aspose.Words pour .NET. Le document résultant sera enregistré sous un nouveau nom




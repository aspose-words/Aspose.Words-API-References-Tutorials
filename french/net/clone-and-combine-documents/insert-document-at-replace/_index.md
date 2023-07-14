---
title: Insérer le document au remplacement
linktitle: Insérer le document au remplacement
second_title: API de traitement de documents Aspose.Words
description: Apprenez à insérer un document lors du remplacement à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/clone-and-combine-documents/insert-document-at-replace/
---

Dans ce didacticiel, nous vous expliquerons comment insérer un document dans un autre document lors du remplacement à l'aide de la fonction Insérer un document lors du remplacement d'Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et effectuer l'insertion du document.

## Étape 1 : Chargement du document principal

Pour commencer, spécifiez le répertoire de vos documents et chargez le document principal dans un objet Document. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Étape 2 : Configurer les options de recherche et de remplacement

Nous allons maintenant configurer les options de recherche et de remplacement en spécifiant le sens de recherche et le rappel de remplacement pour insérer un document dans un autre document. Voici comment:

```csharp
// Configurez les options de recherche et de remplacement.
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## Étape 3 : Appel de la méthode de remplacement

Nous allons maintenant appeler la méthode replace pour rechercher et remplacer le texte spécifié par une chaîne vide, en utilisant les options configurées. Voici comment:

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### Exemple de code source pour Insérer un document à remplacer à l'aide de Aspose.Words pour .NET

Voici le code source complet de la fonction Insérer un document lors du remplacement d'Aspose.Words pour .NET :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

// Définissez les options de recherche et de remplacement.
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

// Appelez la méthode de remplacement.
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```
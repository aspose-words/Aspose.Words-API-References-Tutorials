---
title: Afficher les erreurs de grammaire et d'orthographe
linktitle: Afficher les erreurs de grammaire et d'orthographe
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour activer l'affichage des fautes de grammaire et d'orthographe dans un document avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

Dans ce didacticiel, nous vous guiderons à travers le code source C # pour activer l'affichage des erreurs grammaticales et orthographiques avec Aspose.Words pour .NET. Cette fonctionnalité vous permet d'afficher les fautes de grammaire et d'orthographe dans un document.

## Étape 1 : configuration du projet

Pour commencer, créez un nouveau projet C# dans votre IDE préféré. Assurez-vous que la bibliothèque Aspose.Words pour .NET est référencée dans votre projet.

## Étape 2 : Chargement du document

Dans cette étape, nous allons charger le document Word pour lequel nous voulons afficher les fautes de grammaire et d'orthographe. Utilisez le code suivant pour charger le document :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin réel du répertoire où se trouve votre document.

## Étape 3 : Activer l'affichage des erreurs

Nous allons maintenant activer l'affichage des fautes de grammaire et d'orthographe dans le document. Utilisez le code suivant pour activer l'affichage des erreurs :

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

Ce code permet d'afficher les fautes de grammaire (`ShowGrammaticalErrors`) et les fautes d'orthographe (`ShowSpellingErrors`) dans le document.

### Exemple de code source pour Afficher les erreurs de grammaire et d'orthographe à l'aide de Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

 Assurez-vous de spécifier le bon chemin d'accès au document dans le`dataDir` variable.

Vous avez maintenant appris à activer l'affichage des fautes de grammaire et d'orthographe dans un document à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape fourni dans ce didacticiel, vous pouvez facilement activer cette fonctionnalité dans vos propres documents.
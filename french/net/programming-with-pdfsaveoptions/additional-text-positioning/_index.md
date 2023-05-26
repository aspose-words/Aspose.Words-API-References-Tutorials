---
title: Positionnement supplémentaire du texte
linktitle: Positionnement supplémentaire du texte
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à contrôler le placement de texte supplémentaire lors de la conversion de documents Word en PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/additional-text-positioning/
---

Dans ce didacticiel, nous vous expliquerons les étapes à suivre pour utiliser la fonctionnalité de positionnement de texte supplémentaire avec Aspose.Words pour .NET. Cette fonctionnalité vous permet de contrôler le placement de texte supplémentaire lors de la conversion d'un document Word en PDF. Suivez les étapes ci-dessous :

## Étape 1 : Chargement du document

Commencez par télécharger le document Word que vous souhaitez convertir en PDF :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assurez-vous de spécifier le chemin d'accès correct à votre document Word.

## Étape 2 : Définir les options de conversion PDF

Créez une instance de la classe PdfSaveOptions et activez le positionnement de texte supplémentaire :

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { AdditionalTextPositioning = true };
```

Cette option contrôle le positionnement précis du texte supplémentaire dans le PDF.

## Étape 3 : Convertir le document en PDF

 Utilisez le`Save` méthode pour convertir le document Word en PDF en spécifiant les options de conversion :

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);
```

Assurez-vous de spécifier le chemin d'accès correct pour enregistrer le PDF converti.

### Exemple de code source pour le positionnement de texte supplémentaire à l'aide d'Aspose.Words pour .NET

Voici le code source complet pour utiliser la fonctionnalité de positionnement de texte supplémentaire avec Aspose.Words pour .NET :


```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { AdditionalTextPositioning = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);

```
En suivant ces étapes, vous pouvez facilement contrôler le positionnement du texte supplémentaire lors de la conversion d'un document Word en PDF avec Aspose.Words pour .NET.


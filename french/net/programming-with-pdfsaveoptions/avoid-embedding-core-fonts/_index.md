---
title: Évitez d'incorporer des polices de base
linktitle: Évitez d'incorporer des polices de base
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment éviter l'incorporation de polices de base lors de la conversion de documents Word en PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

Dans ce didacticiel, nous vous expliquerons les étapes à suivre pour utiliser la fonctionnalité Éviter l'incorporation de polices de base avec Aspose.Words pour .NET. Cette fonctionnalité vous permet de contrôler si les polices de base telles que Arial, Times New Roman, etc. doivent être intégrées dans le PDF lors de la conversion d'un document Word. Suivez les étapes ci-dessous :

## Étape 1 : Chargement du document

Commencez par télécharger le document Word que vous souhaitez convertir en PDF :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assurez-vous de spécifier le chemin d'accès correct à votre document Word.

## Étape 2 : Définir les options de conversion PDF

Créez une instance de la classe PdfSaveOptions et activez l'évitement d'incorporation de polices de base :

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

Cette option contrôle si les polices de base doivent être incorporées dans le PDF ou non.

## Étape 3 : Convertir le document en PDF

 Utilisez le`Save` méthode pour convertir le document Word en PDF en spécifiant les options de conversion :

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

Assurez-vous de spécifier le chemin d'accès correct pour enregistrer le PDF converti.

### Exemple de code source pour éviter d'incorporer des polices de base à l'aide d'Aspose.Words pour .NET

Voici le code source complet pour utiliser la fonctionnalité afin d'éviter l'intégration des polices de base avec Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Le PDF de sortie ne sera pas intégré aux polices de base telles que Arial, Times New Roman, etc.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

En suivant ces étapes, vous pouvez facilement contrôler si les polices de base doivent être incorporées dans le PDF lors de la conversion d'un document Word avec Aspose.Words pour .NET.


---
title: Rendu Dml 3DEffects
linktitle: Rendu Dml 3DEffects
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment activer le rendu des effets DML 3D lors de la conversion au format PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

Dans ce tutoriel, nous vous guiderons à travers les étapes pour activer le rendu d'effet DML 3D lors de la conversion en PDF avec Aspose.Words pour .NET. Cela permet de conserver les effets 3D dans le document PDF généré. Suivez les étapes ci-dessous :

## Étape 1 : Chargement du document

Commencez par télécharger le document que vous souhaitez convertir en PDF :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assurez-vous de spécifier le chemin d'accès correct à votre document.

## Étape 2 : Configurer les options d'enregistrement PDF

Créez une instance de la classe PdfSaveOptions et activez le rendu avancé des effets DML 3D :

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

Cette option conserve les effets 3D dans le document PDF généré.

## Étape 3 : Convertir le document en PDF

 Utilisez le`Save` méthode pour convertir le document en PDF en spécifiant les options d'enregistrement :

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

Assurez-vous de spécifier le chemin d'accès correct pour enregistrer le PDF converti.

### Exemple de code source pour le rendu Dml 3DEffects à l'aide de Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

En suivant ces étapes, vous pouvez facilement activer le rendu des effets DML 3D lors de la conversion au format PDF avec Aspose.Words pour .NET.




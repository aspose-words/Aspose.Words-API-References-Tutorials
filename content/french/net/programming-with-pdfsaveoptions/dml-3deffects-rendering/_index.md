---
title: Rendre les effets 3D DML 3DEffects dans un document PDF
linktitle: Rendre les effets 3D DML 3DEffects dans un document PDF
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment activer le rendu des effets DML 3D lors de la conversion au format PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

Dans ce didacticiel, nous vous guiderons à travers les étapes pour activer le rendu de l'effet DML 3D lors de la conversion en PDF avec Aspose.Words pour .NET. Cela conserve les effets 3D dans le document PDF généré. Suivez les étapes ci-dessous :

## Étape 1 : Chargement du document

Commencez par télécharger le document que vous souhaitez convertir en PDF :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assurez-vous de spécifier le chemin correct vers votre document.

## Étape 2 : Configurer les options d'enregistrement PDF

Créez une instance de la classe PdfSaveOptions et activez le rendu avancé des effets DML 3D :

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

Cette option conserve les effets 3D dans le document PDF généré.

## Étape 3 : Convertir le document en PDF

 Utilisez le`Save` méthode pour convertir le document en PDF en spécifiant les options d'enregistrement :

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

Assurez-vous de spécifier le chemin correct pour enregistrer le PDF converti.

### Exemple de code source pour le rendu Dml 3DEffects à l'aide d'Aspose.Words pour .NET

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

En suivant ces étapes, vous pouvez facilement activer le rendu des effets DML 3D lors de la conversion en PDF avec Aspose.Words pour .NET.

## Conclusion

Dans ce didacticiel, nous avons expliqué comment activer le rendu des effets DML 3D lors de la conversion en PDF avec Aspose.Words pour .NET. En suivant les étapes décrites, vous pouvez facilement conserver les effets 3D dans le document PDF généré. Utilisez cette fonctionnalité pour préserver les effets visuels importants de votre document original.


### Questions fréquemment posées

#### Q : Qu'est-ce que le rendu des effets DML 3D dans un document PDF ?
R : Le rendu des effets DML 3D dans un document PDF fait référence à la possibilité de conserver les effets 3D lors de la conversion d'un document au format PDF. Cela préserve les effets visuels et garantit que le document PDF généré ressemble au document original.

#### Q : Comment puis-je activer le rendu des effets DML 3D lors de la conversion au format PDF avec Aspose.Words pour .NET ?
R : Pour activer le rendu des effets DML 3D lors de la conversion au format PDF avec Aspose.Words for .NET, suivez ces étapes :

 Créez une instance du`Document` classe spécifiant le chemin d’accès au document Word.

 Créez une instance du`PdfSaveOptions` classe et définir le`Dml3DEffectsRenderingMode`propriété à`Dml3DEffectsRenderingMode.Advanced` pour activer le rendu avancé des effets DML 3D.

 Utilisez le`Save` méthode du`Document`classe pour enregistrer le document au format PDF en spécifiant les options d'enregistrement.

#### Q : Comment puis-je vérifier si les effets DML 3D ont été rendus dans le document PDF généré ?
R : Pour vérifier si les effets DML 3D ont été rendus dans le document PDF généré, ouvrez le fichier PDF avec une visionneuse PDF compatible, telle qu'Adobe Acrobat Reader, et examinez le document. Vous devriez voir les effets 3D tels qu'ils apparaissent dans le document original.




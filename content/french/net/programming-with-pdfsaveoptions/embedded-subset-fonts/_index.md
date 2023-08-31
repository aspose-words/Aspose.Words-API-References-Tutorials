---
title: Incorporer des polices de sous-ensemble dans un document PDF
linktitle: Incorporer des polices de sous-ensemble dans un document PDF
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour intégrer des sous-ensembles de polices dans un document PDF à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

Cet article fournit un guide étape par étape sur la façon d’utiliser la fonctionnalité d’intégration de sous-ensembles de polices avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. A la fin de ce tutoriel, vous serez en mesure de comprendre comment intégrer des sous-ensembles de polices dans un document et générer un PDF contenant uniquement les glyphes utilisés dans le document.

Avant de commencer, assurez-vous d'avoir installé et configuré la bibliothèque Aspose.Words for .NET dans votre projet. Vous pouvez trouver la bibliothèque et les instructions d'installation sur le site Web d'Aspose.

## Étape 1 : Définir le répertoire des documents

 Pour commencer, vous devez définir le chemin d’accès au répertoire où se trouvent vos documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Téléchargez le document

Ensuite, nous devons charger le document que nous voulons traiter. Dans cet exemple, nous supposons que le document s'appelle « Rendering.docx » et se trouve dans le répertoire de documents spécifié.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Étape 3 : Configurer les options d'enregistrement au format PDF

 Pour créer un PDF contenant uniquement les sous-ensembles de polices utilisés dans le document, nous devons configurer le`PdfSaveOptions` objet avec le`EmbedFullFonts` propriété définie sur`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## Étape 4 : Enregistrez le document au format PDF avec des sous-ensembles de polices

 Enfin, nous pouvons enregistrer le document au format PDF en utilisant les sous-ensembles de polices. Spécifiez le nom du fichier de sortie et le`saveOptions` objet que nous avons configuré à l’étape précédente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

C'est tout ! Vous avez réussi à intégrer des sous-ensembles de polices dans un document et à générer un PDF contenant uniquement les glyphes utilisés dans le document avec Aspose.Words for .NET.

### Exemple de code source pour intégrer des sous-ensembles de polices avec Aspose.Words for .NET

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Le PDF de sortie contiendra des sous-ensembles des polices du document.
	// Seuls les glyphes utilisés dans le document sont inclus dans les polices PDF.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## Conclusion

Dans ce didacticiel, nous avons appris à intégrer des sous-ensembles de polices dans un document PDF à l'aide d'Aspose.Words pour .NET. L'intégration de sous-ensembles de polices permet de réduire la taille du fichier PDF tout en préservant l'apparence du document en utilisant uniquement les caractères réellement utilisés. Cela garantit une meilleure compatibilité et de meilleures performances lors de la visualisation et de l’impression du PDF. N'hésitez pas à explorer davantage les fonctionnalités d'Aspose.Words for .NET pour optimiser la génération de vos documents PDF avec des sous-ensembles de polices intégrés.

### Questions fréquemment posées

#### Q : Qu'est-ce que l'intégration de sous-ensembles de polices dans un document PDF ?
R : L'intégration de sous-ensembles de polices dans un document PDF consiste à inclure uniquement les glyphes utilisés dans le document, plutôt que d'inclure toutes les polices complètes. Cela réduit la taille du fichier PDF en incluant uniquement les données de police nécessaires pour afficher les caractères réellement utilisés dans le document.

#### Q : Quelle est la différence entre l’intégration de polices complètes et l’intégration de sous-ensembles de polices ?
R : L'intégration complète des polices signifie inclure toutes les polices utilisées dans le document dans le fichier PDF, ce qui garantit que le document sera affiché exactement tel qu'il a été conçu, mais peut augmenter la taille du fichier PDF. En revanche, l'intégration de sous-ensembles de polices contient uniquement les glyphes utilisés dans le document, réduisant ainsi la taille du fichier PDF, mais limitant la capacité de reproduire exactement l'apparence du document si des caractères supplémentaires sont ajoutés ultérieurement.

#### Q : Comment puis-je intégrer des sous-ensembles de polices dans un document PDF à l'aide d'Aspose.Words for .NET ?
R : Pour intégrer des sous-ensembles de polices dans un document PDF à l'aide d'Aspose.Words for .NET, procédez comme suit :

 Définissez le chemin du répertoire du document en remplaçant`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel de votre répertoire de documents.

 Chargez le document que vous souhaitez traiter à l'aide du`Document` classe et le chemin du document.

 Configurez les options d'enregistrement PDF en créant une instance du`PdfSaveOptions` classe et définir le`EmbedFullFonts` propriété à`false`Cela garantit que seuls les sous-ensembles de polices utilisés dans le document seront inclus dans le fichier PDF.

 Enregistrez le document au format PDF avec les sous-ensembles de polices intégrés à l'aide du`Save` méthode du`Document` objet, spécifiant le nom du fichier de sortie et les options de sauvegarde configurées précédemment.

#### Q : Quels sont les avantages de l’intégration de sous-ensembles de polices dans un document PDF ?
R : Les avantages de l'intégration de sous-ensembles de polices dans un document PDF sont :

Taille du fichier PDF réduite : en incluant uniquement les glyphes utilisés dans le document, la taille du fichier PDF est réduite par rapport à l'intégration de polices complètes.

Préservation de l'apparence du document : Les sous-ensembles de polices inclus dans le fichier PDF permettent de reproduire l'apparence du document en utilisant uniquement les caractères réellement utilisés.

Compatibilité avec les restrictions de licence : l'intégration de sous-ensembles de polices peut être préférée dans les cas où les polices complètes ne peuvent pas être légalement intégrées en raison de restrictions de licence.
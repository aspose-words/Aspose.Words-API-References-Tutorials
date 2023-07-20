---
title: Réduire la taille du PDF en désactivant les polices intégrées
linktitle: Réduire la taille du PDF en désactivant les polices intégrées
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment réduire la taille du PDF en désactivant l'incorporation de polices Windows lors de la conversion de documents au format PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

Dans ce didacticiel, nous vous expliquerons les étapes à suivre pour réduire la taille du PDF en désactivant l'incorporation de polices Windows dans un document PDF avec Aspose.Words pour .NET. En désactivant l'incorporation des polices, vous pouvez réduire la taille du fichier PDF généré. Suivez les étapes ci-dessous :

## Étape 1 : Chargement du document

Commencez par télécharger le document que vous souhaitez convertir en PDF :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assurez-vous de spécifier le chemin d'accès correct à votre document.

## Étape 2 : Définir les options d'enregistrement PDF

Créez une instance de la classe PdfSaveOptions et spécifiez comment incorporer les polices :

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

Cette option permet de désactiver l'intégration des polices Windows dans le fichier PDF généré.

## Étape 3 : Convertir le document en PDF

 Utilisez le`Save` méthode pour convertir le document en PDF en spécifiant les options de conversion :

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Assurez-vous de spécifier le chemin d'accès correct pour enregistrer le PDF converti.

### Exemple de code source pour désactiver les polices Windows intégrées à l'aide de Aspose.Words pour .NET

Voici le code source complet pour désactiver l'intégration des polices Windows dans un document PDF avec Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Le PDF de sortie sera enregistré sans incorporer les polices Windows standard.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
En suivant ces étapes, vous pouvez facilement désactiver l'incorporation des polices Windows dans un document PDF avec Aspose.Words pour .NET.


## Conclusion

Dans ce didacticiel, nous avons appris à réduire la taille d'un fichier PDF en désactivant l'intégration des polices Windows à l'aide de Aspose.Words pour .NET. En désactivant l'incorporation des polices, vous pouvez réduire la taille du fichier PDF généré, ce qui facilite le stockage, le partage et le transfert de fichiers. Cependant, il est important de noter que la désactivation de l'incorporation des polices Windows peut entraîner des changements d'apparence et de formatage dans le document PDF final. Assurez-vous de tenir compte de ces conséquences lorsque vous utilisez cette fonction. N'hésitez pas à explorer plus de fonctionnalités d'Aspose.Words pour .NET afin d'optimiser la génération de vos fichiers PDF.

### Questions fréquemment posées

#### Q : Qu'est-ce que la désactivation de l'incorporation de polices Windows dans un document PDF et pourquoi est-ce important ?
R : La désactivation de l'incorporation des polices Windows dans un document PDF consiste à empêcher l'inclusion des polices Windows dans le fichier PDF généré. Cela réduit la taille du fichier PDF en supprimant les données de police Windows intégrées. Cela peut être important pour réduire la taille des fichiers PDF, ce qui peut faciliter leur stockage, leur partage et leur transfert plus rapide.

#### : Comment puis-je désactiver l'incorporation de polices Windows dans un document PDF à l'aide d'Aspose.Words pour .NET ?
R : Pour désactiver l'intégration des polices Windows dans un document PDF à l'aide d'Aspose.Words pour .NET, suivez ces étapes :

 Chargez le document que vous souhaitez convertir en PDF à l'aide du`Document` chemin de classe et de document.

 Créer une instance de`PdfSaveOptions`classe et définissez la`FontEmbeddingMode` propriété à`PdfFontEmbeddingMode.EmbedNone`. Cela désactive l'intégration des polices Windows dans le fichier PDF généré.

 Utilisez le`Save` méthode de la`Document` objet pour convertir le document en PDF en spécifiant les options de conversion configurées précédemment.

#### Q : Quels sont les avantages de la désactivation de l'incorporation des polices Windows dans un document PDF ?
R : Les avantages de la désactivation de l'incorporation de polices Windows dans un document PDF sont :

Taille de fichier PDF réduite : en désactivant l'incorporation de polices Windows, les données de police Windows incorporées sont supprimées, ce qui réduit la taille du fichier PDF généré.

Stockage plus facile : les fichiers PDF plus petits sont plus faciles à stocker, enregistrer et transférer.

Partage et transfert plus rapides : les fichiers PDF plus petits peuvent être partagés et transférés plus rapidement, ce qui permet d'économiser du temps et des ressources.

#### : Quelles sont les conséquences de la désactivation de l'incorporation de polices Windows dans un document PDF ?
R : La désactivation de l'intégration des polices Windows dans un document PDF peut avoir des conséquences telles que :

Perte d'apparence et de formatage : si les polices Windows spécifiées dans le document ne sont pas disponibles sur le système sur lequel le PDF est ouvert, des polices de remplacement seront utilisées, ce qui peut entraîner une apparence et un formatage incorrects. forme différente de celles attendues.

Problèmes de lisibilité : Si les polices de substitution utilisées ne sont pas aussi lisibles que les polices d'origine, cela peut affecter la lisibilité du texte dans le document PDF.
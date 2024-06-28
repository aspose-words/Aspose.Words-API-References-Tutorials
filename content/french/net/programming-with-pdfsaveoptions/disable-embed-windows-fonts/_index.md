---
title: Réduisez la taille du PDF en désactivant les polices intégrées
linktitle: Réduisez la taille du PDF en désactivant les polices intégrées
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment réduire la taille d'un PDF en désactivant l'intégration des polices Windows lors de la conversion de documents au format PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

Dans ce didacticiel, nous vous expliquerons les étapes permettant de réduire la taille d'un PDF en désactivant l'intégration des polices Windows dans un document PDF avec Aspose.Words pour .NET. En désactivant l'intégration des polices, vous pouvez réduire la taille du fichier PDF généré. Suivez les étapes ci-dessous :

## Étape 1 : Chargement du document

Commencez par télécharger le document que vous souhaitez convertir en PDF :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assurez-vous de spécifier le chemin correct vers votre document.

## Étape 2 : Définir les options d'enregistrement au format PDF

Créez une instance de la classe PdfSaveOptions et spécifiez comment intégrer les polices :

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

Cette option permet de désactiver l'intégration des polices Windows dans le fichier PDF généré.

## Étape 3 : Convertir le document en PDF

 Utilisez le`Save` méthode pour convertir le document en PDF en spécifiant les options de conversion :

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Assurez-vous de spécifier le chemin correct pour enregistrer le PDF converti.

### Exemple de code source pour désactiver l'intégration des polices Windows à l'aide d'Aspose.Words pour .NET

Voici le code source complet pour désactiver l'intégration des polices Windows dans un document PDF avec Aspose.Words for .NET :

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Le PDF de sortie sera enregistré sans intégrer les polices Windows standard.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
En suivant ces étapes, vous pouvez facilement désactiver l'intégration des polices Windows dans un document PDF avec Aspose.Words pour .NET.


## Conclusion

Dans ce didacticiel, nous avons appris comment réduire la taille d'un fichier PDF en désactivant l'intégration des polices Windows à l'aide d'Aspose.Words pour .NET. En désactivant l'intégration des polices, vous pouvez réduire la taille du fichier PDF généré, facilitant ainsi le stockage, le partage et le transfert de fichiers. Cependant, il est important de noter que la désactivation de l'intégration des polices Windows peut entraîner des modifications de l'apparence et du formatage du document PDF final. Assurez-vous de prendre en compte ces conséquences lorsque vous utilisez cette fonctionnalité. N'hésitez pas à explorer davantage de fonctionnalités d'Aspose.Words for .NET pour optimiser la génération de vos fichiers PDF.

### Questions fréquemment posées

#### Q : Qu'est-ce qui désactive l'intégration des polices Windows dans un document PDF et pourquoi est-ce important ?
R : La désactivation de l'intégration des polices Windows dans un document PDF consiste à empêcher les polices Windows d'être incluses dans le fichier PDF généré. Cela réduit la taille du fichier PDF en supprimant les données de police Windows intégrées. Cela peut être important pour réduire la taille des fichiers PDF, ce qui peut faciliter leur stockage, leur partage et leur transfert plus rapide.

#### Q : Comment puis-je désactiver l'intégration des polices Windows dans un document PDF à l'aide d'Aspose.Words pour .NET ?
R : Pour désactiver l'intégration des polices Windows dans un document PDF à l'aide d'Aspose.Words for .NET, procédez comme suit :

 Chargez le document que vous souhaitez convertir en PDF à l'aide du`Document` chemin de classe et de document.

 Créez une instance du`PdfSaveOptions` classe et définir le`FontEmbeddingMode`propriété à`PdfFontEmbeddingMode.EmbedNone`. Cela désactive l'intégration des polices Windows dans le fichier PDF généré.

 Utilisez le`Save` méthode du`Document` objet pour convertir le document en PDF en spécifiant les options de conversion configurées précédemment.

#### Q : Quels sont les avantages de désactiver l’intégration des polices Windows dans un document PDF ?
R : Les avantages de la désactivation de l'intégration des polices Windows dans un document PDF sont les suivants :

Taille du fichier PDF réduite : en désactivant l'intégration des polices Windows, les données de police Windows intégrées sont supprimées, réduisant ainsi la taille du fichier PDF généré.

Stockage plus facile : les fichiers PDF plus petits sont plus faciles à stocker, à enregistrer et à transférer.

Partage et transfert plus rapides : les fichiers PDF plus petits peuvent être partagés et transférés plus rapidement, économisant ainsi du temps et des ressources.

#### Q : Quelles sont les conséquences de la désactivation de l'intégration des polices Windows dans un document PDF ?
R : La désactivation de l'intégration des polices Windows dans un document PDF peut entraîner les conséquences suivantes :

Perte d'apparence et de formatage : si les polices Windows spécifiées dans le document ne sont pas disponibles sur le système sur lequel le PDF est ouvert, des polices de remplacement seront utilisées, ce qui peut entraîner une apparence et un formatage incorrects. de forme différente de celles attendues.

Problèmes de lisibilité : si les polices de substitution utilisées ne sont pas aussi lisibles que les polices d'origine, cela peut affecter la lisibilité du texte dans le document PDF.
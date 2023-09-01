---
title: Optimisez la taille du PDF en ignorant les polices Arial et Times Roman intégrées
linktitle: Optimisez la taille du PDF en ignorant les polices Arial et Times Roman intégrées
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour générer des PDF optimisés sans intégrer les polices Arial et Times Roman avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

Cet article fournit un guide étape par étape sur la façon d'utiliser la fonctionnalité pour optimiser la taille du PDF en ignorant les polices Arial et Times Roman intégrées à la taille du métafichier avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. A la fin de ce tutoriel, vous pourrez comprendre comment configurer l'option de mode d'incorporation des polices dans un document et générer un PDF sans intégrer les polices Arial et Times Roman.

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

## Étape 3 : Configurer les options d'enregistrement au format PDF avec intégration de polices

 Pour éviter l'intégration des polices Arial et Times Roman dans le PDF généré, nous devons configurer le`PdfSaveOptions` objet et définissez le`FontEmbeddingMode` propriété à`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## Étape 4 : Enregistrez le document au format PDF sans polices intégrées

Enfin, nous pouvons enregistrer le document au format PDF en utilisant les options de sauvegarde configurées précédemment.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

C'est tout ! Vous avez généré avec succès un PDF sans intégrer les polices Arial et Times Roman à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour ignorer les polices Arial et Times Roman intégrées à la taille du métafichier avec Aspose.Words pour .NET

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment désactiver l'intégration des polices Arial et Times Roman dans un document PDF à l'aide d'Aspose.Words pour .NET. En suivant les étapes décrites, vous pouvez générer un fichier PDF sans intégrer ces polices spécifiques, ce qui peut contribuer à réduire la taille du fichier et à garantir une meilleure compatibilité des documents sur différentes plates-formes. Assurez-vous de prendre en compte les conséquences de la désactivation de l'intégration des polices lors de l'utilisation de cette fonctionnalité. N'hésitez pas à explorer davantage de fonctionnalités d'Aspose.Words for .NET pour optimiser la génération de vos fichiers PDF.

### Questions fréquemment posées

#### Q : Qu'est-ce qui désactive l'intégration des polices Arial et Times Roman dans un document PDF et pourquoi est-ce important ?
R : La désactivation de l'intégration des polices Arial et Times Roman dans un document PDF consiste à ne pas inclure ces polices dans le fichier PDF généré. Cela peut être important pour réduire la taille du fichier PDF en évitant d'inclure des polices déjà couramment disponibles sur les systèmes de lecture PDF. Cela peut également contribuer à garantir une meilleure compatibilité et une apparence cohérente du document PDF sur différents appareils et plates-formes.

#### Q : Comment puis-je configurer Aspose.Words pour .NET pour qu'il n'intègre pas les polices Arial et Times Roman dans un document PDF ?
R : Pour configurer Aspose.Words for .NET afin qu'il n'intègre pas les polices Arial et Times Roman dans un document PDF, procédez comme suit :

 Définissez le chemin du répertoire où se trouvent vos documents en remplaçant`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel de votre répertoire de documents.

 Chargez le document que vous souhaitez traiter à l'aide du`Document` classe et le chemin du document spécifié.

 Créez une instance du`PdfSaveOptions` classe et définir le`FontEmbeddingMode` propriété à`PdfFontEmbeddingMode.EmbedAll`. Cela intégrera toutes les polices sauf Arial et Times Roman dans le fichier PDF généré.

 Utilisez le`Save` méthode du`Document` objet pour enregistrer le document au format PDF en précisant les options d'enregistrement configurées précédemment.

#### Q : Quels sont les avantages de la désactivation de l'intégration des polices Arial et Times Roman dans un document PDF ?
R : Les avantages de la désactivation de l'intégration des polices Arial et Times Roman dans un document PDF sont :

Réduction de la taille des fichiers PDF : en évitant d'incorporer des polices couramment disponibles comme Arial et Times Roman, la taille des fichiers PDF peut être réduite, ce qui facilite le stockage, le partage et le transfert de fichiers.

Meilleure compatibilité : en utilisant des polices couramment disponibles sur les systèmes de lecture PDF, vous garantissez une meilleure compatibilité et une meilleure apparence du document sur différents appareils et plates-formes.

#### Q : Quelles sont les conséquences de la désactivation de l'intégration des polices Arial et Times Roman dans un document PDF ?
R : Les conséquences de la désactivation de l'intégration des polices Arial et Times Roman dans un document PDF sont les suivantes :

Apparence différente : si les polices Arial et Times Roman ne sont pas disponibles sur le système sur lequel le PDF est ouvert, des polices de remplacement seront utilisées, ce qui peut donner une apparence différente de celle prévue.

Problèmes de lisibilité : les polices de remplacement utilisées peuvent ne pas être aussi lisibles que les polices d'origine, ce qui peut affecter la lisibilité du document.
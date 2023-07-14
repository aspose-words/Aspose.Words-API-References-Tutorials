---
title: Réduire la taille du fichier PDF en n'incorporant pas les polices de base
linktitle: Réduire la taille du fichier PDF en n'incorporant pas les polices de base
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment réduire la taille du fichier PDF en n'incorporant pas les polices de base lors de la conversion de documents Word en PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

Dans ce didacticiel, nous vous expliquerons comment réduire la taille du fichier PDF en n'incorporant pas les polices de base avec Aspose.Words pour .NET. Cette fonctionnalité vous permet de contrôler si les polices de base telles que Arial, Times New Roman, etc. doivent être intégrées dans le PDF lors de la conversion d'un document Word. Suivez les étapes ci-dessous :

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


## Conclusion

Dans ce didacticiel, nous avons expliqué comment réduire la taille d'un fichier PDF en n'incorporant pas de polices de base avec Aspose.Words pour .NET. Cette fonctionnalité vous permet de contrôler si les polices de base doivent être incorporées dans le PDF lors de la conversion d'un document Word. En suivant les étapes décrites, vous pouvez facilement contrôler l'intégration ou la non-intégration des polices de base, ce qui peut aider à réduire la taille du fichier PDF et assurer une meilleure compatibilité et un aspect cohérent du document sur différents appareils et plates-formes. N'oubliez pas de considérer les conséquences de ne pas incorporer les polices de base et d'expérimenter pour vous assurer que le document s'affiche comme prévu.

### Questions fréquemment posées

#### Q : Quelle est l'option permettant de ne pas incorporer les polices de base dans un fichier PDF et pourquoi est-ce important ?
: L'option de ne pas incorporer les polices de base dans un fichier PDF contrôle si les polices de base telles que Arial, Times New Roman, etc. doivent être incorporées dans le PDF lors de la conversion d'un document Word. Cela peut être important pour réduire la taille du fichier PDF en évitant d'inclure les polices couramment disponibles sur les systèmes de lecture PDF. Cela peut également aider à assurer une meilleure compatibilité et une apparence cohérente du document PDF sur différents appareils et plates-formes.

#### Q : Comment puis-je configurer Aspose.Words pour .NET pour ne pas incorporer les polices de base dans un fichier PDF ?
R : Pour configurer Aspose.Words pour .NET afin qu'il n'intègre pas les polices principales dans un fichier PDF, suivez ces étapes :

 Définissez le chemin du répertoire où se trouvent vos documents en remplaçant`"YOUR DOCUMENTS DIRECTORY"` avec le chemin réel de votre répertoire de documents.

 Chargez le document Word que vous souhaitez convertir en PDF à l'aide du`Document` class et le chemin d'accès au document spécifié.

 Créer une instance de`PdfSaveOptions`classe et définissez la`UseCoreFonts` propriété à`true`. Cela évitera l'incorporation de polices de base dans le fichier PDF généré.

 Utilisez le`Save` méthode de la`Document` objet pour enregistrer le document au format PDF en précisant les options de conversion configurées précédemment.

#### Q : Quels sont les avantages de ne pas incorporer les polices de base dans un fichier PDF ?
R : Les avantages de ne pas incorporer les polices de base dans un fichier PDF sont :

Réduction de la taille du fichier PDF : en évitant d'incorporer des polices couramment disponibles comme Arial, Times New Roman, etc., la taille du fichier PDF peut être réduite, ce qui facilite le stockage, le partage et le transfert de fichiers.

Meilleure compatibilité : en utilisant des polices de base couramment disponibles sur les systèmes de lecture PDF, vous garantissez une meilleure compatibilité et une meilleure apparence des documents sur différents appareils et plates-formes.

#### Q : Quelles sont les conséquences de la non-intégration des polices de base dans un fichier PDF ?
R : Les conséquences de la non-intégration des polices de base dans un fichier PDF sont les suivantes :

Apparence différente : Si les polices de base ne sont pas disponibles sur le système où le PDF est ouvert, des polices de remplacement seront utilisées, ce qui peut entraîner une apparence différente de celle prévue.

Problèmes de lisibilité : les polices de remplacement utilisées peuvent ne pas être aussi lisibles que les polices d'origine, ce qui peut affecter la lisibilité du document.
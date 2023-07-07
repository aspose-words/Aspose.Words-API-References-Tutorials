---
title: Mettre à jour la dernière propriété imprimée dans le document PDF
linktitle: Mettre à jour la dernière propriété imprimée dans le document PDF
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour mettre à jour la propriété "Dernière impression" lors de la conversion au format PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

Cet article fournit un guide étape par étape sur l'utilisation de la propriété "Dernière impression" dans la fonctionnalité de mise à jour de document PDF avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. A la fin de ce tutoriel, vous serez en mesure de comprendre comment paramétrer l'option de mise à jour de la propriété "Dernière impression" lors de la conversion en PDF.

Avant de commencer, assurez-vous d'avoir installé et configuré la bibliothèque Aspose.Words pour .NET dans votre projet. Vous pouvez trouver la bibliothèque et les instructions d'installation sur le site Web d'Aspose.

## Étape 1 : Définir le répertoire des documents

 Pour commencer, vous devez définir le chemin vers le répertoire où se trouvent vos documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Téléchargez le document

Ensuite, nous devons charger le document que nous voulons traiter. Dans cet exemple, nous supposons que le document s'appelle "Rendering.docx" et se trouve dans le répertoire de documents spécifié.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Étape 3 : Configurer les options d'enregistrement au format PDF avec la propriété "Dernière impression" mise à jour

 Pour activer la mise à jour de la propriété "Dernière impression" lors de la conversion en PDF, nous devons configurer le`PdfSaveOptions` objet et définissez le`UpdateLastPrintedProperty` propriété à`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## Étape 4 : Enregistrez le document au format PDF avec la mise à jour de la propriété "Dernière impression"

Enfin, nous pouvons enregistrer le document au format PDF en utilisant les options d'enregistrement configurées précédemment.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

C'est tout ! Vous avez activé avec succès la mise à jour de la propriété "Dernière impression" lors de la conversion d'un document au format PDF à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour la mise à jour de la propriété "Dernier imprimé" avec Aspose.Words pour .NET


```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
## Conclusion

Dans ce didacticiel, nous avons expliqué comment mettre à jour la propriété "Dernière impression" dans un document PDF à l'aide d'Aspose.Words pour .NET. En suivant les étapes indiquées, vous pouvez facilement configurer l'option de mise à jour de la propriété "Dernière impression" lors de la conversion d'un document en PDF. Utilisez cette fonctionnalité pour suivre l'utilisation des documents et les informations associées.

### Questions fréquemment posées

#### Q : Qu'est-ce que la propriété "Dernière impression" dans un document PDF ?
R : La propriété "Dernière impression" d'un document PDF fait référence à la date et à l'heure de la dernière impression du document. Cette propriété peut être utile pour suivre les informations sur l'utilisation et la gestion des documents.

#### Q : Comment puis-je mettre à jour la propriété "Dernière impression" dans un document PDF avec Aspose.Words pour .NET ?
R : Pour mettre à jour la propriété "Dernière impression" dans un document PDF avec Aspose.Words pour .NET, suivez ces étapes :

 Créer une instance de`Document` classe spécifiant le chemin d'accès au document Word.

 Créer une instance de`PdfSaveOptions` classe et définissez la`UpdateLastPrintedProperty` propriété à`true` pour activer la mise à jour de la propriété "Dernière impression".

 Utilisez le`Save` méthode de la`Document`classe pour enregistrer le document au format PDF en spécifiant les options d'enregistrement.

#### Q : Comment puis-je vérifier si la propriété "Dernière impression" a été mise à jour dans le document PDF généré ?
R : Vous pouvez vérifier si la propriété "Dernière impression" a été mise à jour dans le document PDF généré en ouvrant le fichier PDF avec une visionneuse PDF compatible, telle qu'Adobe Acrobat Reader, et en affichant les informations du document. La date et l'heure de la dernière impression doivent correspondre à la date et l'heure de génération du document PDF.

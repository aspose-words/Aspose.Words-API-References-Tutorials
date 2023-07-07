---
title: Définir les options de contour dans un document PDF
linktitle: Définir les options de contour dans un document PDF
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour définir les options de plan dans un document PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/set-outline-options/
---

Cet article fournit un guide étape par étape sur la façon d'utiliser les options de contour définies pour la fonctionnalité de taille de métafichier avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. À la fin de ce didacticiel, vous serez en mesure de comprendre comment définir les options de contour dans un document et générer un PDF avec les options de contour correspondantes.

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

## Étape 3 : Configurer les options d'enregistrement au format PDF avec les options de plan

 Pour définir les options de contour dans le PDF généré, nous devons configurer le`PdfSaveOptions` objet. Nous pouvons définir le nombre de niveaux de contour de titre (`HeadingsOutlineLevels`) et le nombre de niveaux hiérarchiques développés (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## Étape 4 : Enregistrer le document au format PDF avec les options de plan

Enfin, nous pouvons enregistrer le document au format PDF en utilisant les options d'enregistrement configurées précédemment.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

C'est tout ! Vous avez défini avec succès les options de plan dans un document et généré un PDF avec les options de plan correspondantes à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour définir les options de plan sur la taille du métafichier avec Aspose.Words pour .NET


```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment définir les options de plan dans un document PDF à l'aide de Aspose.Words pour .NET. En suivant les étapes décrites, vous pouvez facilement spécifier les niveaux de titre et de plan dans votre document et générer un fichier PDF avec les options de plan correspondantes. Profitez des avantages de l'option de contour pour améliorer la structure et la navigation dans vos documents PDF en utilisant Aspose.Words pour .NET.

### Questions fréquemment posées

#### Q : Qu'est-ce que l'option de contour dans un document PDF ?
: L'option de plan dans un document PDF fait référence à la structure hiérarchique du contenu du document. Il permet de créer une table des matières interactive et facilite la navigation dans le document. Les options de plan déterminent les niveaux de titre et de sous-titre à inclure dans le plan et le niveau de détail à afficher dans le plan généré.

#### Q : Comment puis-je définir des options de plan dans un document PDF à l'aide d'Aspose.Words pour .NET ?
R : Pour définir les options de plan dans un document PDF à l'aide d'Aspose.Words pour .NET, suivez ces étapes :

 Définissez le chemin du répertoire où se trouvent vos documents en remplaçant`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel de votre répertoire de documents.

 Chargez le document que vous souhaitez convertir en PDF à l'aide du`Document` class et spécifiez le chemin d'accès au document dans le répertoire de documents spécifié.

 Configurez les options d'enregistrement au format PDF en créant une instance du`PdfSaveOptions` classe et en utilisant la`OutlineOptions` propriété pour définir les options de contour. Vous pouvez spécifier le nombre de niveaux de titre à inclure dans le plan à l'aide de la`HeadingsOutlineLevels` propriété et le nombre de niveaux hiérarchiques développés à l'aide de la`ExpandedOutlineLevels` propriété.

 Enregistrez le document au format PDF à l'aide de la`Save` méthode de la`Document`classe spécifiant le chemin et les options d'enregistrement.

#### Q : À quoi sert l'option de plan dans un document PDF ?
R : L'option de plan dans un document PDF vous permet de créer une structure hiérarchique du contenu, ce qui facilite la navigation dans le document et l'accès aux différentes sections. Cela permet aux utilisateurs d'accéder rapidement à des parties spécifiques du document en cliquant sur des entrées dans la table des matières ou le plan. L'option de contour améliore également l'expérience de lecture en fournissant un aperçu de la structure globale du document.

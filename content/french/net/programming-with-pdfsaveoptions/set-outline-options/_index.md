---
title: Définir les options de plan dans un document PDF
linktitle: Définir les options de plan dans un document PDF
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour définir les options de plan dans un document PDF avec Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/set-outline-options/
---

Cet article fournit un guide étape par étape sur la façon d'utiliser les options de plan définies pour la fonctionnalité de taille des métafichiers avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. A la fin de ce didacticiel, vous serez en mesure de comprendre comment définir les options de plan dans un document et générer un PDF avec les options de plan correspondantes.

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

## Étape 3 : Configurez les options d'enregistrement au format PDF avec les options du plan

 Pour définir les options de plan dans le PDF généré, nous devons configurer le`PdfSaveOptions` objet. Nous pouvons définir le nombre de niveaux de plan de titre (`HeadingsOutlineLevels`) et le nombre de niveaux de plan étendus (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## Étape 4 : Enregistrez le document au format PDF avec les options de plan

Enfin, nous pouvons enregistrer le document au format PDF en utilisant les options de sauvegarde configurées précédemment.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

C'est tout ! Vous avez réussi à définir les options de plan dans un document et à générer un PDF avec les options de plan correspondantes à l'aide d'Aspose.Words for .NET.

### Exemple de code source pour définir les options du plan sur la taille du métafichier avec Aspose.Words for .NET


```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment définir les options de plan dans un document PDF à l'aide d'Aspose.Words for .NET. À l'aide des étapes décrites, vous pouvez facilement spécifier les niveaux de titre et de plan dans votre document et générer un fichier PDF avec les options de plan correspondantes. Profitez des avantages de l'option Plan pour améliorer la structure et la navigation dans vos documents PDF à l'aide d'Aspose.Words for .NET.

### Questions fréquemment posées

#### Q : Qu'est-ce que l'option de plan dans un document PDF ?
R : L'option de plan dans un document PDF fait référence à la structure hiérarchique du contenu du document. Il permet de créer une table des matières interactive et facilite la navigation dans le document. Les options de plan déterminent les niveaux de titre et de sous-titres à inclure dans le plan ainsi que le niveau de détail à afficher dans le plan généré.

#### Q : Comment puis-je définir les options de plan dans un document PDF à l'aide d'Aspose.Words for .NET ?
R : Pour définir les options de plan dans un document PDF à l'aide d'Aspose.Words for .NET, procédez comme suit :

 Définissez le chemin du répertoire où se trouvent vos documents en remplaçant`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel de votre répertoire de documents.

 Chargez le document que vous souhaitez convertir en PDF à l'aide du`Document` classe et spécifiez le chemin d'accès au document dans le répertoire de documents spécifié.

 Configurez les options d'enregistrement au format PDF en créant une instance du`PdfSaveOptions` classe et en utilisant le`OutlineOptions` propriété pour définir les options de contour. Vous pouvez spécifier le nombre de niveaux de titres à inclure dans le plan à l'aide de l'option`HeadingsOutlineLevels` propriété et le nombre de niveaux de plan développés à l'aide de la`ExpandedOutlineLevels` propriété.

 Enregistrez le document au format PDF à l'aide du`Save` méthode du`Document`classe spécifiant le chemin et les options de sauvegarde.

#### Q : À quoi sert l'option de plan dans un document PDF ?
: L'option Plan dans un document PDF vous permet de créer une structure hiérarchique du contenu, ce qui facilite la navigation dans le document et l'accès aux différentes sections. Cela permet aux utilisateurs d'accéder rapidement à des parties spécifiques du document en cliquant sur les entrées de la table des matières ou du plan. L'option de plan améliore également l'expérience de lecture en fournissant un aperçu de la structure globale du document.

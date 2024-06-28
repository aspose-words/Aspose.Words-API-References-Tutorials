---
title: Réduisez la taille du PDF en adaptant les polices Wmf à la taille du métafichier
linktitle: Réduisez la taille du PDF en adaptant les polices Wmf à la taille du métafichier
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour réduire la taille du PDF en adaptant les polices WMF à la taille du métafichier lors de la conversion en PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

Cet article fournit un guide étape par étape sur la façon de réduire la taille d'un PDF avec la fonction de mise à l'échelle des polices WMF en fonction de la taille des métafichiers avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. À la fin de ce didacticiel, vous serez en mesure de comprendre comment activer ou désactiver la mise à l'échelle des polices WMF lors de la conversion en PDF.

Avant de commencer, assurez-vous d'avoir installé et configuré la bibliothèque Aspose.Words for .NET dans votre projet. Vous pouvez trouver la bibliothèque et les instructions d'installation sur le site Web d'Aspose.

## Étape 1 : Définir le répertoire des documents

 Pour commencer, vous devez définir le chemin d’accès au répertoire où se trouvent vos documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Téléchargez le document

Ensuite, nous devons charger le document que nous voulons traiter. Dans cet exemple, nous supposons que le document s'appelle « WMF with text.docx » et se trouve dans le répertoire de documents spécifié.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## Étape 3 : Configurer les options de rendu des métafichiers

 Pour activer ou désactiver la mise à l'échelle des polices WMF en fonction de la taille du métafichier, nous devons configurer le`MetafileRenderingOptions` objet. Dans cet exemple, nous désactivons la mise à l'échelle des polices en définissant le`ScaleWmfFontsToMetafileSize`propriété à`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## Étape 4 : Configurer les options d'enregistrement au format PDF avec les options de rendu des métafichiers

Enfin, nous pouvons configurer les options d'enregistrement au format PDF à l'aide des options de rendu des métafichiers configurées précédemment.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## Étape 5 : Enregistrez le document au format PDF avec les options de rendu des métafichiers

Enregistrez le document au format PDF en utilisant les options d'enregistrement précédemment configurées.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

C'est tout ! Vous avez activé ou désactivé avec succès la mise à l'échelle de la police WMF en fonction de la taille du métafichier lors de la conversion.

un document PDF utilisant Aspose.Words pour .NET.

### Exemple de code source pour mettre à l'échelle les polices WMF à la taille du métafichier avec Aspose.Words pour .NET

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	//Si Aspose.Words ne peut pas restituer correctement certains enregistrements de métafichier en graphiques vectoriels
	// puis Aspose.Words restitue ce métafichier en bitmap.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment activer ou désactiver le redimensionnement des polices WMF à la taille d'un métafichier dans un document PDF à l'aide d'Aspose.Words pour .NET. En suivant les étapes décrites, vous pouvez facilement contrôler si les polices WMF doivent être redimensionnées pour correspondre à la taille du métafichier lors de la conversion en document PDF. Cela peut vous aider à réduire la taille du fichier PDF généré et à améliorer les performances de rendu. Assurez-vous de spécifier le chemin correct vers vos documents et de configurer les options de rendu des métafichiers selon vos besoins.

### Questions fréquemment posées

#### Q : Qu'est-ce que le redimensionnement des polices WMF à la taille d'un métafichier dans un document PDF ?
R : Le redimensionnement des polices WMF à la taille du métafichier dans un document PDF est une fonctionnalité qui contrôle si les polices WMF doivent être mises à l'échelle pour correspondre à la taille du métafichier lors de la conversion en document PDF. Lorsque cette fonctionnalité est activée, les polices WMF sont mises à l'échelle pour correspondre à la taille du métafichier, ce qui peut réduire la taille du document PDF généré.

#### Q : Comment puis-je utiliser Aspose.Words for .NET pour activer ou désactiver le redimensionnement des polices WMF à la taille d'un métafichier dans un document PDF ?
R : Pour activer ou désactiver le redimensionnement des polices WMF à la taille d'un métafichier dans un document PDF à l'aide d'Aspose.Words for .NET, procédez comme suit :

 Définissez le chemin du répertoire où se trouvent vos documents en remplaçant`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel de votre répertoire de documents.

 Chargez le document que vous souhaitez traiter à l'aide du`Document` classe et spécifiez le chemin d’accès au document Word dans le répertoire de documents spécifié.

 Configurez les options de rendu des métafichiers en créant une instance du`MetafileRenderingOptions` classe et définir le`ScaleWmfFontsToMetafileSize`propriété à`true` pour activer la mise à l'échelle des polices WMF à la taille du métafichier, ou pour`false` pour désactiver cette fonctionnalité.

 Configurez les options d'enregistrement au format PDF en créant une instance du`PdfSaveOptions` classe et en utilisant les options de rendu de métafichier configurées précédemment.

 Enregistrez le document au format PDF à l'aide du`Save` méthode du`Document` classe spécifiant le chemin et les options de sauvegarde.

#### Q : Quels sont les avantages du redimensionnement des polices WMF à la taille d'un métafichier dans un document PDF ?
R : Les avantages du redimensionnement des polices WMF à la taille d'un métafichier dans un document PDF sont :

Réduction de la taille du fichier PDF : le redimensionnement des polices WMF à la taille du métafichier peut réduire la taille du document PDF généré en adaptant la taille de la police aux besoins du métafichier.

Performances améliorées : en ajustant la taille des polices WMF aux dimensions du métafichier, le rendu du document PDF peut être plus rapide et plus efficace.
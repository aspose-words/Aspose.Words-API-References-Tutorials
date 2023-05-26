---
title: Toutes les polices intégrées
linktitle: Toutes les polices intégrées
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour incorporer toutes les polices dans un PDF en utilisant Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/embedded-all-fonts/
---

Cet article fournit un guide étape par étape sur l'utilisation de la fonctionnalité Embedded All Fonts d'Aspose.Words pour .NET. Nous allons parcourir l'extrait de code et expliquer chaque partie en détail. À la fin de ce didacticiel, vous serez en mesure de comprendre comment incorporer toutes les polices dans un document et générer un PDF avec les polices incorporées à l'aide d'Aspose.Words pour .NET.

Avant de commencer, assurez-vous que la bibliothèque Aspose.Words pour .NET est installée et configurée dans votre projet. Vous pouvez trouver la bibliothèque et les instructions d'installation sur le site Web d'Aspose.

## Étape 1 : Définissez le chemin d'accès au répertoire de documents

Pour commencer, vous devez définir le chemin d'accès au répertoire où se trouvent vos documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Chargez le document

Ensuite, nous devons charger le document que nous voulons traiter. Dans cet exemple, nous supposons que le document s'appelle "Rendering.docx" et se trouve dans le répertoire de documents spécifié.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Étape 3 : Configurez les options d'enregistrement PDF

 Pour intégrer toutes les polices dans le PDF résultant, nous devons configurer le`PdfSaveOptions` objet avec le`EmbedFullFonts` propriété définie sur`true`. Cela garantit que toutes les polices utilisées dans le document sont incluses dans le fichier PDF généré.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = true };
```

## Étape 4 : Enregistrez le document au format PDF avec des polices intégrées

 Enfin, nous pouvons enregistrer le document sous forme de fichier PDF avec les polices intégrées. Spécifiez le nom du fichier de sortie et le`saveOptions` objet que nous avons configuré à l'étape précédente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
```

C'est ça! Vous avez intégré avec succès toutes les polices dans un document et généré un PDF avec les polices intégrées à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour Embedded All Fonts utilisant Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Le PDF de sortie sera intégré avec toutes les polices trouvées dans le document.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
  
```

## Conclusion

Dans ce didacticiel, nous avons couvert le processus étape par étape d'utilisation de la fonctionnalité Embedded All Fonts d'Aspose.Words pour .NET. Nous avons appris à charger un document, à configurer les options d'enregistrement PDF et à enregistrer le document sous forme de fichier PDF avec des polices intégrées. En suivant ce guide, vous pouvez vous assurer que vos documents PDF intègrent toutes les polices nécessaires, offrant un rendu cohérent et précis sur différents appareils et plates-formes.

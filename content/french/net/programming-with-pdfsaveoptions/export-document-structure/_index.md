---
title: Exporter la structure d'un document Word vers un document PDF
linktitle: Exporter la structure d'un document Word vers un document PDF
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour exporter la structure d’un document Word vers un document PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/export-document-structure/
---

Cet article fournit un guide étape par étape sur la façon d'utiliser la fonctionnalité Exporter la structure d'un document Word vers un document PDF avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. A la fin de ce tutoriel, vous pourrez comprendre comment exporter la structure d'un document et générer un PDF avec la structure du document visible.

Avant de commencer, assurez-vous d'avoir installé et configuré la bibliothèque Aspose.Words for .NET dans votre projet. Vous pouvez trouver la bibliothèque et les instructions d'installation sur le site Web d'Aspose.

## Étape 1 : Définir le répertoire des documents

 Pour commencer, vous devez définir le chemin d’accès au répertoire où se trouvent vos documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Téléchargez le document

Ensuite, nous devons charger le document que nous voulons traiter. Dans cet exemple, nous supposons que le document s'appelle « Paragraphs.docx » et se trouve dans le répertoire de documents spécifié.

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## Étape 3 : Configurer les options d'enregistrement au format PDF

 Pour exporter la structure du document et la rendre visible dans le volet de navigation « Contenu » d'Adobe Acrobat Pro lors de l'édition du fichier PDF, nous devons configurer le`PdfSaveOptions` objet avec le`ExportDocumentStructure` propriété définie sur`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## Étape 4 : Enregistrez le document au format PDF avec la structure du document

Enfin, nous pouvons enregistrer le document au format PDF en utilisant les options de sauvegarde configurées précédemment.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

C'est tout ! Vous avez exporté avec succès une structure de document et généré un PDF avec la structure du document visible à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour exporter la structure d'un document avec Aspose.Words for .NET


```csharp

            // Le chemin d'accès au répertoire des documents.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            // La taille du fichier sera augmentée et la structure sera visible dans le volet de navigation "Contenu"
            // d'Adobe Acrobat Pro, lors de l'édition du .pdf.
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```


## Conclusion

Dans ce didacticiel, nous avons expliqué comment exporter la structure d'un document Word vers un document PDF à l'aide d'Aspose.Words pour .NET. En suivant les étapes décrites, vous pouvez facilement générer un PDF avec la structure de votre document visible, ce qui facilite la navigation et la recherche dans le document. Utilisez les fonctionnalités d'Aspose.Words for .NET pour exporter la structure de vos documents Word et créer des PDF bien structurés.

### Questions fréquemment posées

#### Q : Qu'est-ce que l'exportation de la structure d'un document Word vers un document PDF ?
: L'exportation de la structure d'un document Word vers un document PDF crée un PDF avec une structure de document visible. La structure du document comprend généralement des éléments tels que des titres, des sections, des paragraphes et d'autres éléments structurés du document. Cette structure peut être utile pour la navigation et la recherche dans le document PDF.

#### Q : Comment puis-je exporter la structure d'un document Word vers un document PDF à l'aide d'Aspose.Words pour .NET ?
R : Pour exporter la structure d'un document Word vers un document PDF à l'aide d'Aspose.Words for .NET, suivez ces étapes :

 Créez une instance du`Document` classe spécifiant le chemin d’accès au document Word.

 Créez une instance du`PdfSaveOptions` classe et définir le`ExportDocumentStructure` propriété à`true`. Cela exportera la structure du document et la rendra visible dans le volet de navigation « Contenu » d'Adobe Acrobat Pro lors de la modification du fichier PDF.

 Utilisez le`Save` méthode du`Document`classe pour enregistrer le document au format PDF en spécifiant les options d'enregistrement.

#### Q : Comment puis-je afficher la structure d'un document PDF avec Adobe Acrobat Pro ?
R : Pour afficher la structure d'un document PDF avec Adobe Acrobat Pro, procédez comme suit :

Ouvrez le document PDF dans Adobe Acrobat Pro.

Dans la barre de navigation de gauche, cliquez sur l'icône « Contenu » pour afficher le volet de navigation « Contenu ».

Dans le volet de navigation « Contenu », vous verrez la structure du document avec des titres, des sections et d'autres éléments structurés.
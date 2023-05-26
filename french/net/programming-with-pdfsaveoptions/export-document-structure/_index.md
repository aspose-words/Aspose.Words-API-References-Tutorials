---
title: Exporter la structure du document
linktitle: Exporter la structure du document
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour exporter la structure d'un document avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/export-document-structure/
---

Cet article fournit un guide étape par étape sur l'utilisation de la fonctionnalité Exporter la structure du document avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. A la fin de ce tutoriel, vous serez en mesure de comprendre comment exporter la structure d'un document et générer un PDF avec la structure du document visible.

Avant de commencer, assurez-vous d'avoir installé et configuré la bibliothèque Aspose.Words pour .NET dans votre projet. Vous pouvez trouver la bibliothèque et les instructions d'installation sur le site Web d'Aspose.

## Étape 1 : Définir le répertoire des documents

 Pour commencer, vous devez définir le chemin vers le répertoire où se trouvent vos documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Téléchargez le document

Ensuite, nous devons charger le document que nous voulons traiter. Dans cet exemple, nous supposons que le document s'appelle "Paragraphs.docx" et se trouve dans le répertoire de documents spécifié.

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## Étape 3 : Configurer les options d'enregistrement au format PDF

 Pour exporter la structure du document et rendre la structure visible dans le volet de navigation "Contenu" d'Adobe Acrobat Pro lors de l'édition du fichier PDF, nous devons configurer le`PdfSaveOptions` objet avec le`ExportDocumentStructure` propriété définie sur`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## Étape 4 : Enregistrez le document au format PDF avec la structure du document

Enfin, nous pouvons enregistrer le document au format PDF en utilisant les options d'enregistrement configurées précédemment.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

C'est tout ! Vous avez exporté avec succès une structure de document et généré un PDF avec la structure de document visible à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour exporter la structure du document avec Aspose.Words pour .NET


```csharp

            // Chemin d'accès au répertoire des documents.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            // La taille du fichier sera augmentée et la structure sera visible dans le volet de navigation "Contenu"
            // d'Adobe Acrobat Pro, lors de l'édition du fichier .pdf.
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```

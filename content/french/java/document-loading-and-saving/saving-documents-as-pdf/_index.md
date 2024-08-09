---
title: Enregistrement de documents au format PDF dans Aspose.Words pour Java
linktitle: Enregistrer des documents au format PDF
second_title: API de traitement de documents Java Aspose.Words
description: Découvrez comment enregistrer des documents Word au format PDF à l'aide d'Aspose.Words pour Java. Personnalisez les polices, les propriétés et la qualité de l'image. Un guide complet pour la conversion PDF.
type: docs
weight: 22
url: /fr/java/document-loading-and-saving/saving-documents-as-pdf/
---

## Introduction à l'enregistrement de documents au format PDF dans Aspose.Words pour Java

Dans ce guide étape par étape, nous explorerons comment enregistrer des documents au format PDF à l'aide d'Aspose.Words pour Java. Nous aborderons divers aspects de la conversion PDF et fournirons des exemples de code pour faciliter le processus.

## Conditions préalables

Avant de commencer, assurez-vous que vous disposez des conditions préalables suivantes :

- Kit de développement Java (JDK) installé sur votre système.
-  Bibliothèque Aspose.Words pour Java. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/words/java/).

## Conversion d'un document en PDF

Pour convertir un document Word en PDF, vous pouvez utiliser l'extrait de code suivant :

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

 Remplacer`"input.docx"` avec le chemin d'accès à votre document Word et`"output.pdf"` avec le chemin du fichier PDF de sortie souhaité.

## Contrôle des options d'enregistrement PDF

 Vous pouvez contrôler diverses options d'enregistrement PDF à l'aide du`PdfSaveOptions` classe. Par exemple, vous pouvez définir le titre d'affichage du document PDF comme suit :

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDisplayDocTitle(true);
doc.save("output.pdf", saveOptions);
```

## Incorporation de polices dans un PDF

Pour intégrer des polices dans le PDF généré, utilisez le code suivant :

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

## Personnalisation des propriétés du document

Vous pouvez personnaliser les propriétés du document dans le PDF généré. Par exemple:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

## Exportation de la structure du document

 Pour exporter la structure du document, définissez le`exportDocumentStructure` possibilité de`true`:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setExportDocumentStructure(true);
doc.save("output.pdf", saveOptions);
```

## Compression d'images

Vous pouvez contrôler la compression des images à l'aide du code suivant :

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setImageCompression(PdfImageCompression.JPEG);
doc.save("output.pdf", saveOptions);
```

## Mise à jour de la dernière propriété imprimée

Pour mettre à jour la propriété « Dernière impression » dans le PDF, utilisez :

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setUpdateLastPrintedProperty(true);
doc.save("output.pdf", saveOptions);
```

## Rendu des effets 3D DML

Pour un rendu avancé des effets 3D DML, définissez le mode de rendu :

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDml3DEffectsRenderingMode(Dml3DEffectsRenderingMode.ADVANCED);
doc.save("output.pdf", saveOptions);
```

## Interpolation d'images

Vous pouvez activer l'interpolation d'image pour améliorer la qualité de l'image :

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setInterpolateImages(true);
doc.save("output.pdf", saveOptions);
```

## Conclusion

Aspose.Words for Java offre des fonctionnalités complètes pour convertir des documents Word au format PDF avec des options de flexibilité et de personnalisation. Vous pouvez contrôler divers aspects de la sortie PDF, notamment les polices, les propriétés du document, la compression des images, etc.

## FAQ

### Comment convertir un document Word en PDF à l'aide d'Aspose.Words pour Java ?

Pour convertir un document Word en PDF, utilisez le code suivant :

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

 Remplacer`"input.docx"` avec le chemin d'accès à votre document Word et`"output.pdf"` avec le chemin du fichier PDF de sortie souhaité.

### Puis-je intégrer des polices dans le PDF généré par Aspose.Words for Java ?

 Oui, vous pouvez intégrer des polices dans le PDF en définissant l'option`setEmbedFullFonts` possibilité de`true` dans`PdfSaveOptions`. Voici un exemple :

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

### Comment puis-je personnaliser les propriétés du document dans le PDF généré ?

 Vous pouvez personnaliser les propriétés du document dans le PDF à l'aide de l'outil`setCustomPropertiesExport` choix dans`PdfSaveOptions`. Par exemple:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

### Quel est le but de la compression d’image dans Aspose.Words pour Java ?

 La compression d'image vous permet de contrôler la qualité et la taille des images dans le PDF généré. Vous pouvez définir le mode de compression de l'image en utilisant`setImageCompression` dans`PdfSaveOptions`.

### Comment mettre à jour la propriété « Dernière impression » dans le PDF ?

 Vous pouvez mettre à jour la propriété « Dernière impression » dans le PDF en définissant`setUpdateLastPrintedProperty` à`true` dans`PdfSaveOptions`. Cela reflétera la dernière date d'impression dans les métadonnées PDF.

### Comment puis-je améliorer la qualité de l’image lors de la conversion au format PDF ?

 Pour améliorer la qualité de l'image, activez l'interpolation d'image en définissant`setInterpolateImages` à`true` dans`PdfSaveOptions`. Cela se traduira par des images plus fluides et de meilleure qualité dans le PDF.
---
title: Joindre et ajouter des documents dans Aspose.Words pour Java
linktitle: Joindre et annexer des documents
second_title: API de traitement de documents Java Aspose.Words
description: Apprenez à joindre et à ajouter des documents sans effort à l'aide d'Aspose.Words pour Java. Préservez la mise en forme, gérez les en-têtes, les pieds de page, et bien plus encore.
type: docs
weight: 30
url: /fr/java/document-manipulation/joining-and-appending-documents/
---

## Introduction à la jointure et à l'ajout de documents dans Aspose.Words pour Java

Dans ce didacticiel, nous verrons comment joindre et ajouter des documents à l'aide de la bibliothèque Aspose.Words pour Java. Vous apprendrez à fusionner de manière transparente plusieurs documents tout en préservant le formatage et la structure.

## Conditions préalables

Avant de commencer, assurez-vous que l'API Aspose.Words pour Java est configurée dans votre projet Java.

## Options de jonction de documents

### Ajout simple

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Ajouter avec les options de format d'importation

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

### Ajouter au document vierge

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document();
dstDoc.removeAllChildren();
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Ajouter avec conversion du numéro de page

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
convertNumPageFieldsToPageRef(dstDoc); // Convertir les champs NUMPAGES
dstDoc.updatePageLayout(); // Mettre à jour la mise en page pour une numérotation correcte
```

## Gestion de différentes mises en page

Lors de l'ajout de documents avec des mises en page différentes :

```java
srcDoc.getFirstSection().getPageSetup().setSectionStart(SectionStart.CONTINUOUS);
srcDoc.getFirstSection().getPageSetup().setRestartPageNumbering(true);
// Assurez-vous que les paramètres de mise en page correspondent au document de destination
```

## Joindre des documents avec différents styles

```java
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES);
```

## Comportement de style intelligent

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setSmartStyleBehavior(true);
builder.insertDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

## Insérer des documents avec DocumentBuilder

```java
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.insertDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## Conserver la numérotation des sources

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## Gestion des zones de texte

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setIgnoreTextBoxes(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## Gestion des en-têtes et pieds de page

### Lier les en-têtes et les pieds de page

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Dissocier les en-têtes et les pieds de page

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## Conclusion

Aspose.Words for Java fournit des outils flexibles et puissants pour joindre et ajouter des documents, que vous ayez besoin de conserver le formatage, de gérer différentes mises en page ou de gérer les en-têtes et les pieds de page. Expérimentez ces techniques pour répondre à vos besoins spécifiques en matière de traitement de documents.

## FAQ

### Comment puis-je joindre des documents de styles différents de manière transparente ?

 Pour joindre des documents avec des styles différents, utilisez`ImportFormatMode.USE_DESTINATION_STYLES` lors de l'ajout.

### Puis-je conserver la numérotation des pages lors de l’ajout de documents ?

 Oui, vous pouvez conserver la numérotation des pages en utilisant le`convertNumPageFieldsToPageRef` méthode et mise à jour de la mise en page.

### Qu’est-ce qu’un comportement de style intelligent ?

 Le comportement intelligent des styles permet de maintenir des styles cohérents lors de l'ajout de documents. Utilisez-le avec`ImportFormatOptions` pour de meilleurs résultats.

### Comment puis-je gérer les zones de texte lors de l’ajout de documents ?

Ensemble`importFormatOptions.setIgnoreTextBoxes(false)` pour inclure des zones de texte lors de l'ajout.

### Que faire si je souhaite lier/dissocier les en-têtes et pieds de page entre des documents ?

 Vous pouvez lier les en-têtes et les pieds de page avec`linkToPrevious(true)` ou dissociez-les avec`linkToPrevious(false)` au besoin.
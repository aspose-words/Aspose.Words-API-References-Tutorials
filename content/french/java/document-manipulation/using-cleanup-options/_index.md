---
title: Utilisation des options de nettoyage dans Aspose.Words pour Java
linktitle: Utilisation des options de nettoyage
second_title: API de traitement de documents Java Aspose.Words
description: Améliorez la clarté des documents avec les options de nettoyage d'Aspose.Words pour Java. Découvrez comment supprimer les paragraphes vides, les régions inutilisées et bien plus encore.
type: docs
weight: 10
url: /fr/java/document-manipulation/using-cleanup-options/
---

## Introduction à l'utilisation des options de nettoyage dans Aspose.Words pour Java

Dans ce didacticiel, nous explorerons comment utiliser les options de nettoyage dans Aspose.Words for Java pour manipuler et nettoyer des documents pendant le processus de fusion et de publipostage. Les options de nettoyage vous permettent de contrôler divers aspects du nettoyage du document, tels que la suppression des paragraphes vides, des régions inutilisées, etc.

## Conditions préalables

 Avant de commencer, assurez-vous que la bibliothèque Aspose.Words for Java est intégrée à votre projet. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/words/java/).

## Étape 1 : suppression des paragraphes vides

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insérer des champs de fusion
FieldMergeField mergeFieldOption1 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_1");
mergeFieldOption1.setFieldName("Option_1");
builder.write(" ? ");
FieldMergeField mergeFieldOption2 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_2");
mergeFieldOption2.setFieldName("Option_2");

// Définir les options de nettoyage
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS);

// Activer les paragraphes de nettoyage avec des signes de ponctuation
doc.getMailMerge().setCleanupParagraphsWithPunctuationMarks(true);

// Exécuter le publipostage
doc.getMailMerge().execute(new String[] { "Option_1", "Option_2" }, new Object[] { null, null });

// Enregistrez le document
doc.save("WorkingWithCleanupOptions.CleanupParagraphsWithPunctuationMarks.docx");
```

Dans cet exemple, nous créons un nouveau document, insérons des champs de fusion et définissons les options de nettoyage pour supprimer les paragraphes vides. De plus, nous permettons la suppression des paragraphes contenant des signes de ponctuation. Après l'exécution du publipostage, le document est enregistré avec le nettoyage spécifié appliqué.

## Étape 2 : suppression des régions non fusionnées

```java
Document doc = new Document("Your Directory Path" + "Mail merge destination - Northwind suppliers.docx");
DataSet data = new DataSet();

// Définir les options de nettoyage pour supprimer les régions inutilisées
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS);

// Exécuter un publipostage avec les régions
doc.getMailMerge().executeWithRegions(data);

// Enregistrez le document
doc.save("WorkingWithCleanupOptions.RemoveUnmergedRegions.docx");
```

Dans cet exemple, nous ouvrons un document existant avec des régions de fusion, définissons les options de nettoyage pour supprimer les régions inutilisées, puis exécutons le publipostage avec des données vides. Ce processus supprime automatiquement les régions inutilisées du document.

## Étape 3 : Suppression des champs vides

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Définir les options de nettoyage pour supprimer les champs vides
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_FIELDS);

// Exécuter le publipostage
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Enregistrez le document
doc.save("WorkingWithCleanupOptions.RemoveEmptyFields.docx");
```

Dans cet exemple, nous ouvrons un document avec des champs de fusion, définissons les options de nettoyage pour supprimer les champs vides et exécutons le publipostage avec les données. Après la fusion, tous les champs vides seront supprimés du document.

## Étape 4 : suppression des champs inutilisés

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Définir les options de nettoyage pour supprimer les champs inutilisés
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS);

// Exécuter le publipostage
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Enregistrez le document
doc.save("WorkingWithCleanupOptions.RemoveUnusedFields.docx");
```

Dans cet exemple, nous ouvrons un document avec des champs de fusion, définissons les options de nettoyage pour supprimer les champs inutilisés et exécutons le publipostage avec les données. Après la fusion, tous les champs inutilisés seront supprimés du document.

## Étape 5 : Suppression des champs conteneurs

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Définir les options de nettoyage pour supprimer les champs conteneurs
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS);

// Exécuter le publipostage
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Enregistrez le document
doc.save("WorkingWithCleanupOptions.RemoveContainingFields.docx");
```

Dans cet exemple, nous ouvrons un document avec des champs de fusion, définissons les options de nettoyage pour supprimer les champs contenant et exécutons le publipostage avec les données. Après la fusion, les champs eux-mêmes seront supprimés du document.

## Étape 6 : Suppression des lignes de tableau vides

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Définir les options de nettoyage pour supprimer les lignes vides du tableau
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS);

// Exécuter le publipostage
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Enregistrez le document
doc.save("WorkingWithCleanupOptions.RemoveEmptyTableRows.docx");
```

Dans cet exemple, nous ouvrons un document avec un tableau et fusionnons les champs, définissons les options de nettoyage pour supprimer les lignes vides du tableau et exécutons le publipostage avec les données. Après la fusion, toutes les lignes vides du tableau seront supprimées du document.

## Conclusion

Dans ce didacticiel, vous avez appris à utiliser les options de nettoyage dans Aspose.Words for Java pour manipuler et nettoyer des documents pendant le processus de fusion et de publipostage. Ces options offrent un contrôle précis sur le nettoyage des documents, vous permettant de créer facilement des documents soignés et personnalisés.

## FAQ

### Quelles sont les options de nettoyage dans Aspose.Words pour Java ?

Les options de nettoyage dans Aspose.Words pour Java sont des paramètres qui vous permettent de contrôler divers aspects du nettoyage des documents pendant le processus de fusion et de publipostage. Ils vous permettent de supprimer les éléments inutiles tels que les paragraphes vides, les régions inutilisées, etc., garantissant ainsi que votre document final est bien structuré et soigné.

### Comment puis-je supprimer les paragraphes vides de mon document ?

 Pour supprimer les paragraphes vides de votre document à l'aide d'Aspose.Words for Java, vous pouvez définir le`MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS` option à vrai. Cela éliminera automatiquement les paragraphes sans contenu, ce qui donnera un document plus propre.

###  Quel est le but du`REMOVE_UNUSED_REGIONS` cleanup option?

 Le`MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS` L'option est utilisée pour supprimer les régions d'un document qui n'ont pas de données correspondantes pendant le processus de fusion et de publipostage. Il permet de garder votre document bien rangé en éliminant les espaces réservés inutilisés.

### Puis-je supprimer les lignes de tableau vides d’un document à l’aide d’Aspose.Words pour Java ?

 Oui, vous pouvez supprimer les lignes de tableau vides d'un document en définissant l'option`MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS`option de nettoyage sur true. Cela supprimera automatiquement toutes les lignes du tableau qui ne contiennent pas de données, garantissant ainsi un tableau bien structuré dans votre document.

###  Que se passe-t-il lorsque je règle le`REMOVE_CONTAINING_FIELDS` option?

 Réglage du`MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS` L'option supprimera l'intégralité du champ de fusion, y compris le paragraphe qui le contient, du document pendant le processus de fusion et de publipostage. Ceci est utile lorsque vous souhaitez éliminer les champs de fusion et leur texte associé.

### Comment puis-je supprimer les champs de fusion inutilisés de mon document ?

 Pour supprimer les champs de fusion inutilisés d'un document, vous pouvez définir le`MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS` option à vrai. Cela éliminera automatiquement les champs de fusion qui ne sont pas renseignés lors du publipostage, ce qui donnera un document plus propre.

###  Quelle est la différence entre`REMOVE_EMPTY_FIELDS` and `REMOVE_UNUSED_FIELDS` cleanup options?

 Le`REMOVE_EMPTY_FIELDS` L'option supprime les champs de fusion qui ne contiennent aucune donnée ou qui sont vides pendant le processus de fusion et de publipostage. D'un autre côté, le`REMOVE_UNUSED_FIELDS`L'option supprime les champs de fusion qui ne sont pas renseignés avec des données lors de la fusion. Le choix entre eux dépend si vous souhaitez supprimer les champs sans contenu ou ceux qui sont inutilisés dans l'opération de fusion spécifique.

### Comment puis-je activer la suppression des paragraphes contenant des signes de ponctuation ?

 Pour activer la suppression des paragraphes comportant des signes de ponctuation, vous pouvez définir le`cleanupParagraphsWithPunctuationMarks` sur true et spécifiez les signes de ponctuation à prendre en compte pour le nettoyage. Cela vous permet de créer un document plus raffiné en supprimant les paragraphes inutiles contenant uniquement de la ponctuation.

### Puis-je personnaliser les options de nettoyage dans Aspose.Words pour Java ?

Oui, vous pouvez personnaliser les options de nettoyage en fonction de vos besoins spécifiques. Vous pouvez choisir les options de nettoyage à appliquer et les configurer selon vos exigences de nettoyage de document, garantissant ainsi que votre document final répond aux normes souhaitées.
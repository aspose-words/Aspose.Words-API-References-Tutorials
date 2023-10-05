---
title: Klonen und Kombinieren von Dokumenten in Aspose.Words für Java
linktitle: Dokumente klonen und kombinieren
second_title: Aspose.Words Java-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Dokumente in Aspose.Words für Java klonen und kombinieren. Schritt-für-Schritt-Anleitung mit Quellcode-Beispielen.
type: docs
weight: 27
url: /de/java/document-manipulation/cloning-and-combining-documents/
---

## Einführung in das Klonen und Kombinieren von Dokumenten in Aspose.Words für Java

In diesem Tutorial erfahren Sie, wie Sie Dokumente mit Aspose.Words für Java klonen und kombinieren. Wir behandeln verschiedene Szenarien, darunter das Klonen eines Dokuments, das Einfügen von Dokumenten an Ersetzungspunkten, Lesezeichen und bei Serienbriefvorgängen.

## Schritt 1: Ein Dokument klonen

 Um ein Dokument in Aspose.Words für Java zu klonen, können Sie Folgendes verwenden`deepClone()` Methode. Hier ist ein einfaches Beispiel:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
Document clone = doc.deepClone();
clone.save("Your Directory Path" + "CloneAndCombineDocuments.CloningDocument.docx");
```

Dieser Code erstellt einen Deep Clone des Originaldokuments und speichert es als neue Datei.

## Schritt 2: Dokumente an Ersetzungspunkten einfügen

Sie können Dokumente an bestimmten Ersetzungspunkten in ein anderes Dokument einfügen. So können Sie es machen:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
FindReplaceOptions options = new FindReplaceOptions();
options.setDirection(FindReplaceDirection.BACKWARD);
options.setReplacingCallback(new InsertDocumentAtReplaceHandler());
mainDoc.getRange().replace(Pattern.compile("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

 In diesem Beispiel verwenden wir a`FindReplaceOptions` -Objekt, um einen Callback-Handler für die Ersetzung anzugeben. Der`InsertDocumentAtReplaceHandler` Die Klasse übernimmt die Einfügelogik.

## Schritt 3: Dokumente als Lesezeichen einfügen

Um ein Dokument an einem bestimmten Lesezeichen in ein anderes Dokument einzufügen, können Sie den folgenden Code verwenden:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
Document subDoc = new Document("Your Directory Path" + "Document insertion 2.docx");
Bookmark bookmark = mainDoc.getRange().getBookmarks().get("insertionPlace");
insertDocument(bookmark.getBookmarkStart().getParentNode(), subDoc);
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtBookmark.docx");
```

 Hier suchen wir das Lesezeichen nach Namen und verwenden es`insertDocument` Methode zum Einfügen des Inhalts der`subDoc` Dokument an der Lesezeichenposition.

## Schritt 4: Dokumente während des Seriendrucks einfügen

Sie können Dokumente während eines Serienbriefvorgangs in Aspose.Words für Java einfügen. Hier ist wie:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
mainDoc.getMailMerge().setFieldMergingCallback(new InsertDocumentAtMailMergeHandler());
mainDoc.getMailMerge().execute(new String[] { "Document_1" }, new Object[] { "Your Directory Path" + "Document insertion 2.docx" });
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

 In diesem Beispiel legen wir einen Rückruf für die Feldzusammenführung mithilfe von fest`InsertDocumentAtMailMergeHandler` Klasse, die das Einfügen des im Feld „Document_1“ angegebenen Dokuments verarbeitet.

## Abschluss

Das Klonen und Kombinieren von Dokumenten in Aspose.Words für Java kann mithilfe verschiedener Techniken erfolgen. Unabhängig davon, ob Sie ein Dokument klonen, Inhalte an Ersetzungspunkten, Lesezeichen oder beim Seriendruck einfügen müssen, bietet Aspose.Words leistungsstarke Funktionen zur nahtlosen Bearbeitung von Dokumenten.

## FAQs

### Wie klone ich ein Dokument in Aspose.Words für Java?

 Sie können ein Dokument in Aspose.Words für Java mit klonen`deepClone()` Methode. Hier ist ein Beispiel:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
Document clone = doc.deepClone();
clone.save("Your Directory Path" + "ClonedDocument.docx");
```

### Wie kann ich ein Dokument als Lesezeichen einfügen?

 Um ein Dokument in ein Lesezeichen in Aspose.Words für Java einzufügen, können Sie das Lesezeichen nach Namen suchen und dann verwenden`insertDocument` Methode zum Einfügen des Inhalts. Hier ist ein Beispiel:

```java
Document mainDoc = new Document("Your Directory Path" + "MainDocument.docx");
Document subDoc = new Document("Your Directory Path" + "SubDocument.docx");
Bookmark bookmark = mainDoc.getRange().getBookmarks().get("MyBookmark");
insertDocument(bookmark.getBookmarkStart().getParentNode(), subDoc);
mainDoc.save("Your Directory Path" + "CombinedDocument.docx");
```

### Wie füge ich Dokumente beim Seriendruck in Aspose.Words für Java ein?

Sie können Dokumente während des Seriendrucks in Aspose.Words für Java einfügen, indem Sie einen Rückruf für die Feldzusammenführung festlegen und das einzufügende Dokument angeben. Hier ist ein Beispiel:

```java
Document mainDoc = new Document("Your Directory Path" + "MainDocument.docx");
mainDoc.getMailMerge().setFieldMergingCallback(new InsertDocumentAtMailMergeHandler());
mainDoc.getMailMerge().execute(new String[] { "DocumentField" }, new Object[] { "Your Directory Path" + "DocumentToInsert.docx" });
mainDoc.save("Your Directory Path" + "MergedDocument.docx");
```

 In diesem Beispiel ist die`InsertDocumentAtMailMergeHandler`Die Klasse verwaltet die Einfügelogik für das „DocumentField“ während des Seriendrucks.